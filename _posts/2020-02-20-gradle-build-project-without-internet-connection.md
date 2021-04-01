---
title:  "Build Gradle project without an internet connection"
modified: 2020-02-22T23:00:00+07:00
permalink: /how-to/build-gradle-project-without-an-internet-connection
categories: 
  - How To
tags:
  - Gradle
  - Gradle Build
  - Gradle Local Dependencies
  - Java
---

Most companies usually have a firewall that filters or restricts some domains and hosts. 
Or, your CI/CD environment just only able to access to a tested environment. 
So how to compile your project with dependencies declared. Let try :D

{% include base_path %}
{% include toc title="Table of Contents" %}

## What using in demonstration
> **OS**: macOS 10.14.5<br/>
> **Java**: 1.8.0_211<br/>
> **Gradle**: 6.2<br/>

## Assumptions
I have a build.gradle file by below.
```gradle
import java.nio.charset.StandardCharsets

group group
version version

apply plugin: 'java'
apply plugin: 'idea'    // Optional using for IntelliJ IDEA
apply plugin: 'eclipse' // Optional using for Eclipse
apply plugin: 'io.qameta.allure'

/*
* Define extra properties for the project object - project.ext
*/
ext {
    encoding = StandardCharsets.UTF_8.name()
}

[compileJava, compileTestJava]*.sourceCompatibility = 1.8
[compileJava, compileTestJava]*.targetCompatibility = 1.8
[compileJava, compileTestJava]*.options.collect { options -> options.debug = true }
[compileJava, compileTestJava]*.options.collect { options -> options.encoding = encoding }

repositories {
    jcenter()
    mavenCentral()
    maven {
        url "https://plugins.gradle.org/m2/"
    }
}

dependencies {
    implementation('com.codeborne:selenide:5.6.1')
    implementation('io.qameta.allure:allure-gradle:2.8.1')
    implementation('io.qameta.allure:allure-selenide:2.13.1')

    testImplementation('org.junit.jupiter:junit-jupiter-api:5.6.0')

    compileOnly('org.projectlombok:lombok:1.18.12')
    annotationProcessor('org.projectlombok:lombok:1.18.12')

    testCompileOnly('org.projectlombok:lombok:1.18.12')
    testAnnotationProcessor('org.projectlombok:lombok:1.18.12')
}

buildscript {
    repositories {
        jcenter()
        mavenCentral()
        maven {
            url "https://plugins.gradle.org/m2/"
        }
    }
    dependencies {
        classpath "io.qameta.allure:allure-gradle:2.8.1"
    }
}
```

## Steps
### Add tasks
*Assume you do this step on a machine granted permission, such as your boss PC =))*<br/>

Refers to [download-dependencies-to-local-with-gradle]({{site.baseurl}}/how-to/download-dependencies-to-local-with-gradle)

```gradle
task libsImplementation(type: Sync) {
    from configurations.compileClasspath
    from configurations.runtimeClasspath
    into 'libs/libs-implementation'
}

task libsTestImplementation(type: Sync) {
    from configurations.testCompileClasspath - configurations.compileClasspath
    from configurations.testRuntimeClasspath - configurations.runtimeClasspath
    into 'libs/libs-test-implementation'
}

task libsAnnotationProcessor(type: Sync) {
    from configurations.annotationProcessor + configurations.testAnnotationProcessor
    into 'libs/libs-annotation-processor'
}

task download(dependsOn: ['libsImplementation', 'libsTestImplementation', 'libsAnnotationProcessor'])
```

### Run task and download
```bat
./gradlew download
```
- This task calls tasks `libsImplementation`, `libsTestImplementation`, `libsAnnotationProcessor`.
You don't need to run above 3 tasks in sequence.<br/>
- Your dependencies as JAR files appear in `libs` directory by subfolders
named `libs-implementation`, `libs-test-implementation` and `libs-annotation-processor`.

### Switch to local mode
#### Distribution Url
1. Access [https://gradle.org/releases/](https://gradle.org/releases/){:target="_blank"}
2. Select target version and click `binary-only` link to download (E.g. I select version 6.2)
3. Move downloaded `gradle-6.2-bin.zip` file to `gradle/wrapper` folder
4. Open [gradle/wrapper/gradle-wrapper.properties](https://github.com/ngoanh2n/blog-demo/tree/master/gradle-build-project-without-internet-connection/gradle/wrapper/gradle-wrapper.properties){:target="_blank"} file
5. Change value of `distributionUrl` property to `gradle-6.2-bin.zip`

    ```yml
    distributionBase=GRADLE_USER_HOME
    distributionPath=wrapper/dists
    distributionUrl=gradle-6.2-bin.zip
    zipStoreBase=GRADLE_USER_HOME
    zipStorePath=wrapper/dists
    ```

#### Build Configuration
Replace below scripts in build.gradle file to:

- `repositories {}` script
    <p/>
    ```gradle
    repositories {
        flatDir { dirs 'libs' }
    }
    ```
    <p/>

- `dependencies {}` script
    <p/>
    ```gradle
    dependencies {
        implementation fileTree(dir: 'libs/libs-implementation', include: ['*.jar'])
        testImplementation fileTree(dir: 'libs/libs-test-implementation', include: ['*.jar'])

        compileOnly files('libs/libs-annotation-processor/lombok-1.18.12.jar')
        annotationProcessor files('libs/libs-annotation-processor/lombok-1.18.12.jar')

        testCompileOnly files('libs/libs-annotation-processor/lombok-1.18.12.jar')
        testAnnotationProcessor files('libs/libs-annotation-processor/lombok-1.18.12.jar')
    }
    ```
    <p/>

- `buildscript {}` script
    <p/>
    ```gradle
    buildscript {
        repositories {
            flatDir { dirs 'libs' }
        }
        dependencies {
            classpath files('libs/libs-implementation/allure-gradle:2.8.1.jar')
        }
    }
    ```
    <p/>

### Try to test
Now, you have to build to assure that succeeded.
```bat
./gradlew build
```

Full build.gradle file with online and offline modes:
- [online.gradle](https://github.com/ngoanh2n/blog-demo/tree/master/gradle-build-project-without-internet-connection/gradle/online.gradle){:target="_blank"}
- [offline.gradle](https://github.com/ngoanh2n/blog-demo/tree/master/gradle-build-project-without-internet-connection/gradle/offline.gradle){:target="_blank"}
