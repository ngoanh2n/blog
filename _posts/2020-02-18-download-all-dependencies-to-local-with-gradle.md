---
title:  "Download all dependencies to local with Gradle"
modified: 2020-02-18T23:00:00+07:00
permalink: /how-to/download-all-dependencies-to-local-with-gradle
categories: 
  - How To
tags:
  - Gradle
---

{% include base_path %}
{% include toc title="Getting Started" %}

## Assumption
### Structure
You have a gradle project with structure.
```
blog-demonstrations/download-dependencies-with-gradle
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── src/test
│   ├── java/com/github/ngoanh2n/blog-demonstration
│   │   ├── pkg1
│   │   │   ├── Class1.java
│   │   │   └── Class2.java
│   │   ├── pkg2
│   │   │   └── Class3.java
│   └── resources
├── .gitignore
├── LICENSE
├── README.md
├── build.gradle
├── gradle.properties
├── gradlew
├── gradlew.bat
└── settings.gradle
```

### build.gradle
For example, I'm using 4 dependencies:
- `com.codeborne:selenide:x.x.x`
- `org.junit.jupiter:junit-jupiter-api:x.x.x`
- `org.slf4j:slf4j-api:x.x.x`
- `org.slf4j:slf4j-log4j12:x.x.x`

```gradle
import java.nio.charset.StandardCharsets

/**
 * @author ngoanh2n@gmail.com (Ho Huu Ngoan)
 */

group group
version version

apply plugin: 'java'
apply plugin: 'idea'    // Optional using for IntelliJ IDEA
apply plugin: 'eclipse' // Optional using for Eclipse

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
    implementation('org.slf4j:slf4j-api:1.7.30')

    testImplementation('org.junit.jupiter:junit-jupiter-api:5.6.0')
    testImplementation('org.slf4j:slf4j-log4j12:1.7.30')
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
    }
}
```

## Add task for downloading
1. Task to download all dependencies with declaration `implementation`
```gradle
task libsProd(type: Sync) {
    from configurations.compileClasspath
    into "$buildDir/lib-prod"
}
```

2. Task to download all dependencies with declaration `testImplementation`
```gradle
task libsTest(type: Sync) {
    from configurations.testRuntimeClasspath - configurations.compileClasspath
    into "$buildDir/lib-test"
}
```

## Run tasks
### Using IntelliJ IDEA
- Open this in IntelliJ IDEA
- Navigate **View > Tool Windows > Gradle**
- Expand **Taks > other**
- Double click on the task which you want to execute

<figure class='half_center'>
	<a href="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"><img src="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"></a>
	<figcaption>Now you can see tasks: libsProdand and libsTest</figcaption>
</figure>

### Using command line (terminal)
- cd `blog-demonstrations/download-dependencies-with-gradle`
- `./gradlew libsProd` for implementation dependencies
- `./gradlew libsTest` for implementation testImplementation

**If your machine's OS is Windows:**<br/>
Use `gradlew libsProd` instead.
{: .notice--info}

## Output
So, your downloaded jars (from dependencies) available at `blog-demonstrations/download-dependencies-with-gradle/build` by 2 subfolders named `lib-prod` and `lib-test`.
This means, it also downloads *dependencies tree* - dependencies of 4 dependencies above.

Demonstration project [here](https://github.com/ngoanh2n/blog-demonstrations/tree/master/download-dependencies-with-gradle)
