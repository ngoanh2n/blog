---
title:  "Download dependencies to local with Gradle"
modified: 2020-02-21T23:00:00+07:00
permalink: /how-to/download-dependencies-to-local-with-gradle
categories: 
  - How To
tags:
  - Gradle
  - Gradle Build
  - Gradle Local Dependencies
  - IntelliJ IDEA
  - Java
---

{% include base_path %}
{% include toc title="Table of Contents" %}

## What using in demonstration
> **OS**: macOS 10.14.5<br/>
> **Java**: 1.8.0_211<br/>
> **Gradle**: 6.2<br/>
> **IntelliJ IDEA**: 2019.3.1 (Community Edition)<br/>

> **[TIP]** Gradle version:<br/>
You can change target version by 2 ways (*See [https://gradle.org/releases](https://gradle.org/releases){:target="_blank"}*):
1. Run on command line (terminal):<br/>
`./gradlew wrapper --gradle-version=6.2`<br/>
2. Edit [`gradle-wrapper.properties`](https://github.com/ngoanh2n/blog-demonstrations/blob/master/download-dependencies-with-gradle/gradle/wrapper/gradle-wrapper.properties){:target="_blank"} in `gradle/wrapper` folder<br/>
{: .notice--info}

## Assumptions
### Structure
I have a gradle project with structure.
```
download-dependencies-with-gradle
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── src
│   ├── main
│   │   ├── java
│   │   └── resources
│   └── test
│       ├── java
│       └── resources
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
Type the following command in your command line or terminal.
```console
cd download-dependencies-with-gradle
```

### Dependencies of source set main
Task to download dependencies with `implementation`, `compileOnly`, `runtimeOnly` declarations
```gradle
task libsMain(type: Sync) {
    from configurations.compileClasspath
    from configurations.runtimeClasspath
    into "$buildDir/libs-main"
}
```
Type the following command in your command line or terminal.
```bat
./gradlew libsMain
```

### Dependencies of source set test
Task to download dependencies with `testImplementation`, `testCompileOnly`, `testRuntimeOnly` declarations
```gradle
task libsTest(type: Sync) {
    from configurations.testCompileClasspath - configurations.compileClasspath
    from configurations.testRuntimeClasspath - configurations.runtimeClasspath
    into "$buildDir/libs-test"
}
```
Type the following command in your command line or terminal.
```bat
./gradlew libsTest
```

### All dependencies
Task to download all dependencies with `implementation`, `compileOnly`, `runtimeOnly`, `testImplementation`, `testCompileOnly`, `testRuntimeOnly` declarations
```gradle
task libsAll(type: Sync){
    from configurations.testCompileClasspath
    from configurations.testRuntimeClasspath
    into "$buildDir/libs-all"
}
```
Type the following command in your command line or terminal.
```bat
./gradlew libsAll
```

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
Type the following command in your command line or terminal.
```bat
./gradlew libsConfigurations
```

**[TIP]** If your machine's OS is Windows:<br/>
Use `gradlew [taskName]` instead.
{: .notice--success}

## Run tasks using IntelliJ IDEA
- Open this in IntelliJ IDEA
- Navigate by the following **View > Tool Windows > Gradle**
- Expand **Taks > other**
- Double click on the task which you want to execute

<figure class='half_center'>
	<a href="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"><img src="{{ site.baseurl }}/images/20200218/intelli-gradle-window-tasks-other.png"></a>
	<figcaption>Now you can see tasks: libsMain, libsTest, libsAll and libsConfigurations</figcaption>
</figure>

## Output
So, your downloaded jars (from dependencies) available at `download-dependencies-with-gradle/build` by 4 subfolders named `libs-main`, `libs-test`, `libs-all`, `libs-configurations`
This means, it also downloads *dependencies tree* - dependencies of 2 dependencies above.

**[TIP]** Show dependencies tree:<br/>
Use ```./gradlew :dependencies```
{: .notice--success}

**[SOURCE]** Source code illustrates on Github:<br/>
See or clone [download-dependencies-with-gradle](https://github.com/ngoanh2n/blog-demonstrations/tree/master/download-dependencies-with-gradle){:target="_blank"}
{: .notice--success}
