---
title:  "Download all dependencies to local with Gradle"
modified: 2020-02-21T23:00:00+07:00
permalink: /how-to/download-all-dependencies-to-local-with-gradle
categories: 
  - How To
tags:
  - Gradle
  - Build Tool
  - IntelliJ IDEA
---

{% include base_path %}
{% include toc title="Getting Started" %}

## Assumption
> **Gradle version:**
> *This demo is using Gradle 6.2*<br/>
> You can change version by (*See [https://gradle.org/releases](https://gradle.org/releases)*):<br/>
> 1. Run on command line (terminal): `./gradle wrapper --gradle-version 6.2`<br/>
> 2. Edit `gradle-wrapper.properties` in `gradle/wrapper` folder<br/>
{: .notice--info}

### Structure
I have a gradle project with structure.
```
download-dependencies-with-gradle
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
For example, I'm using 2 dependencies:
- `com.codeborne:selenide:x.x.x`
- `org.junit.jupiter:junit-jupiter-api:x.x.x`

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
    testImplementation('org.junit.jupiter:junit-jupiter-api:5.6.0')
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

## Tasks for downloading
### Dependencies of source set main
Task to download dependencies with `implementation`, `compileOnly`, `runtimeOnly` declarations
```gradle
task libsMain(type: Sync) {
    from configurations.compileClasspath
    from configurations.runtimeClasspath
    into "$buildDir/libs-main"
}
```
Run task from command line (terminal)
- cd `download-dependencies-with-gradle`
- `./gradlew libsMain`

### Dependencies of source set test
Task to download dependencies with `testImplementation`, `testCompileOnly`, `testRuntimeOnly` declarations
```gradle
task libsTest(type: Sync) {
    from configurations.testCompileClasspath - configurations.compileClasspath
    from configurations.testRuntimeClasspath - configurations.runtimeClasspath
    into "$buildDir/libs-test"
}
```
Run task from command line (terminal)
- cd `download-dependencies-with-gradle`
- `./gradlew libsTest`

### All dependencies
Task to download all dependencies with `implementation`, `compileOnly`, `runtimeOnly`, `testImplementation`, `testCompileOnly`, `testRuntimeOnly` declarations
```gradle
task libsAll(type: Sync){
    from configurations.testCompileClasspath
    from configurations.testRuntimeClasspath
    into "$buildDir/libs-all"
}
```
Run task from command line (terminal)
- cd `download-dependencies-with-gradle`
- `./gradlew libsAll`

### Download dependencies with configurations
Task to download dependencies with `implementation`, `testImplementation` configurations
```gradle
configurations {
    implementation
    testImplementation
}

configurations.implementation.setCanBeResolved(true)
configurations.testImplementation.setCanBeResolved(true)

task libsConfigurations(type: Sync){
    from configurations.implementation
    from configurations.testImplementation
    into "$buildDir/libs-configurations"
}
```
Run task from command line (terminal)
- cd `download-dependencies-with-gradle`
- `./gradlew libsConfigurations`

**If your machine's OS is Windows:**<br/>
Use `gradlew [taskName]` instead.
{: .notice--info}

## Run tasks using IntelliJ IDEA
- Open this in IntelliJ IDEA
- Navigate **View > Tool Windows > Gradle**
- Expand **Taks > other**
- Double click on the task which you want to execute

<figure class='half_center'>
	<a href="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"><img src="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"></a>
	<figcaption>Now you can see tasks: libsProd and libsTest</figcaption>
</figure>

## Output
So, your downloaded jars (from dependencies) available at `download-dependencies-with-gradle/build` by 2 subfolders named `libs-main`, `libs-test`, `libs-all`, `libs-configurations`
This means, it also downloads *dependencies tree* - dependencies of 2 dependencies above.

**Show dependencies tree:**<br/>
Run `gradlew :dependencies`
{: .notice--info}

Demonstration project [here](https://github.com/ngoanh2n/blog-demonstrations/tree/master/download-dependencies-with-gradle)
