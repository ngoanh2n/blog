---
title:  "Declare multiple versions of a dependency in Gradle"
modified: 2020-02-28T23:00:00+07:00
permalink: /how-to/declare-multiple-versions-of-a-dependency-in-gradle
categories: 
  - How To
tags:
  - Gradle
  - Gradle Build
  - Dependency Multiple Versions
  - Dependency Management
  - TestNG
  - Allure
  - Java
---

Software projects rarely work in isolation. In most cases, a project relies on reusable functionality in the form of libraries or is broken up into individual components to compose a modularized system. Dependency management is a technique for declaring, resolving and using dependencies required by the project in an automated fashion.<br/>
So, what if I want to use the latest version while there is already a dependency using the old version?

{% include base_path %}
{% include toc title="Table of Contents" %}

## What using in demonstration
> **OS**: macOS 10.14.5<br/>
> **Java**: 1.8.0_211<br/>
> **Gradle**: 6.2.1<br/>
> **IntelliJ IDEA**: 2019.3.1 (Community Edition)<br/>

## Assumptions
I have a build.gradle file with `dependencies {}` script.
- TestNG: `7.1.0`
- Allure TestNG: `2.13.1`

```gradle
dependencies {
    implementation('org.testng:testng:7.1.0')
    implementation('io.qameta.allure:allure-testng:2.13.1')
}
```

And, a test method using above 2 libraries.
```java
package com.github.ngoanh2n;

import io.qameta.allure.Allure;
import org.testng.annotations.Test;

/**
 * @author ngoanh2n@gmail.com (Ho Huu Ngoan)
 */

public class DemonstrationTest {

    @Test
    void test() {
        Allure.step("This is test", () -> {
            System.out.println("Today is 2020-02-28");
        });
    }
}
```

**[SOURCE]** Source code illustrates the conflict between dependencies on Github:<br/>
See or clone [declare-multi-versions-of-a-dependency-in-gradle_conflict](https://github.com/ngoanh2n/blog-demonstrations/tree/master/declare-multi-versions-of-a-dependency-in-gradle_conflict){:target="_blank"}
{: .notice--success}

<!-- ## Why the error occurred -->
## Facing the problem
### Try to test
Let's see the error and solve it!
1. Navigate to the root of this demonstration

    ```console
    cd declare-multi-versions-of-a-dependency-in-gradle_conflict
    ```

2. Try to run test method `DemonstrationTest.test`

    ```bat
    ./gradlew clean test --tests *DemonstrationTest.test
    ```

3. Watch detailed error generated by Gradle

    Open `index.html` file in `build/reports/tests/test/`<br/>
    Of course you will see errors: `java.lang.NoClassDefFoundError: org/testng/IInvokedMethodListener2`

    ```console
    Caused by: java.lang.NoClassDefFoundError: org/testng/IInvokedMethodListener2
        at java.lang.ClassLoader.defineClass1(Native Method)
        at java.lang.ClassLoader.defineClass(ClassLoader.java:763)
        at java.security.SecureClassLoader.defineClass(SecureClassLoader.java:142)
        at java.net.URLClassLoader.defineClass(URLClassLoader.java:468)
        ...
    Caused by: java.lang.ClassNotFoundException: org.testng.IInvokedMethodListener2
        at java.net.URLClassLoader.findClass(URLClassLoader.java:382)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:424)
        at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:349)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:357)
    ```

### Trace the error
This error caused by not finding `org.testng.IInvokedMethodListener2` class.
Let check dependencies tree by following command:
```bat
./gradlew :dependencies
```

> **[TIP]** You can also check on [Maven Repository](https://mvnrepository.com){:target="_blank"}:<br/>
> Access [io.qameta.allure:allure-testng:2.13.1](https://mvnrepository.com/artifact/io.qameta.allure/allure-testng/2.13.1){:target="_blank"}<br/>
> Scroll to `Runtime Dependencies` to see denpendencies version and check it's up to date or not.
{: .notice--info}

And the results:
```
testRuntimeClasspath - Runtime classpath of source set 'test'.
+--- org.testng:testng:7.1.0
|    +--- com.beust:jcommander:1.72
|    +--- com.google.inject:guice:4.1.0
|    |    +--- javax.inject:javax.inject:1
|    |    +--- aopalliance:aopalliance:1.0
|    |    \--- com.google.guava:guava:19.0
|    \--- org.yaml:snakeyaml:1.21
\--- io.qameta.allure:allure-testng:2.13.1
     +--- io.qameta.allure:allure-java-commons:2.13.1
     |    +--- io.qameta.allure:allure-model:2.13.1
     |    |    \--- com.fasterxml.jackson.core:jackson-databind:2.9.8
     |    |         +--- com.fasterxml.jackson.core:jackson-annotations:2.9.0
     |    |         \--- com.fasterxml.jackson.core:jackson-core:2.9.8
     |    +--- org.slf4j:slf4j-api:1.7.25
     |    +--- com.fasterxml.jackson.core:jackson-databind:2.9.8 (*)
     |    +--- org.apache.tika:tika-core:1.20
     |    \--- org.jooq:joor-java-8:0.9.10
     \--- org.testng:testng:6.14.3 -> 7.1.0 (*)
```

Reason:
- You can see `io.qameta.allure:allure-testng:2.13.1` is using `org.testng:testng:6.14.3`
- Meanwhile, I'm deliberately using `org.testng:testng:7.1.0` for this project
- Because source code of `org.testng:testng:6.14.3` was not compliled, `org.testng:testng:7.1.0` is used for compiling into group `org.testng`. And `IInvokedMethodListener2` class was removed in version 7.1.0 of TestNG

## Solving problem
You have to keep multi versions of TestNG:
- `6.14.3` for `allure-testng:2.13.1`
- `7.1.0` as a main test framework for this project

### Declare configurations
Add `implementationTestNG6` and `implementationTestNG7` to `congigurations {}` script by the following:

```gradle
configurations {
    implementationTestNG6
    implementationTestNG7
}
```

### Download both versions
```gradle
/*
* Download dependencies through configurations 'implementationTestNG6' 
* and 'implementationTestNG7' into 'libs' folder
*/
task libs(type: Sync) {
    from configurations.testCompile
    from configurations.implementationTestNG6
    from configurations.implementationTestNG7
    into "$buildDir/libs"
}

/*
* Run task 'libs' automatically when resolving dependencies
*/
classes.dependsOn libs
```

### Declare dependencies using configurations
```gradle
dependencies {
    implementationTestNG7('org.testng:testng:7.1.0')
    implementationTestNG6('org.testng:testng:6.14.3')
    implementation files("$buildDir/libs/testng-6.14.3.jar")
}
```

Now try to run test method `DemonstrationTest.test` again
```bat
./gradlew clean test --tests *DemonstrationTest.test
```

**[SOURCE]** Source code illustrates how to resolve on Github:<br/>
See or clone [declare-multi-versions-of-a-dependency-in-gradle_conflict-resolved](https://github.com/ngoanh2n/blog-demonstrations/tree/master/declare-multi-versions-of-a-dependency-in-gradle_conflict-resolved){:target="_blank"}
{: .notice--success}

**[REFERENCES]** Gradle Docs:<br/>
[https://docs.gradle.org](https://docs.gradle.org){:target="_blank"}
{: .notice--info}
