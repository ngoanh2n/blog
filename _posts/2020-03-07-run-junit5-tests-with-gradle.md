---
title:  "Run JUnit5 or TestNG tests with Gradle"
modified: 2020-03-07T20:00:00+07:00
permalink: /how-to/run-junit5-or-testng-tests-with-gradle
categories: 
  - How To
tags:
  - Gradle
  - JUnit5
  - TestNG
  - Gradle Build
  - Java
  - Test Execution
  - Test Filtering
  - Test Detection
  - Test Grouping
---

This post is dedicated to explaining how Gradle handles differing requirements between and within builds, with significant coverage of how it integrates with the two most common testing frameworks: [JUnit5](https://junit.org/junit5/docs/current/user-guide/){:target="_blank"} and [TestNG](https://testng.org/doc/documentation-main.html){:target="_blank"}.

{% include base_path %}
{% include toc title="Table of Contents" %}

## What using in demonstration
> **OS**: macOS 10.14.5<br/>
> **Java**: 1.8.0_211<br/>
> **Gradle**: 6.2.2<br/>
> **JUnit5 - Jupiter**: 5.6.0<br/>
> **TestNG**: 7.1.0<br/>
> **IntelliJ IDEA**: 2019.3.3 (Community Edition)<br/>

## Declaration
Declare your testing framework at `dependencies {}` script block with `test` scope in `build.gradle` file.
The most useful are `testImplementation` and `testRuntimeOnly` — that the plugins tie into the test task’s classpath.

### JUnit5
#### Compiling and executing JUnit Jupiter tests

```gradle
dependencies {
    testImplementation('org.junit.jupiter:junit-jupiter-api:5.6.0')
    testRuntimeOnly('org.junit.jupiter:junit-jupiter-engine:5.6.0')
}
```

#### Executing legacy tests with JUnit Vintage
If you want to run JUnit 3/4 tests on JUnit Platform, or even mix them with Jupiter tests.
```gradle
dependencies {
    testImplementation('org.junit.jupiter:junit-jupiter-api:5.6.0')
    testRuntimeOnly('org.junit.jupiter:junit-jupiter-engine:5.6.0')
    testCompileOnly('junit:junit:4.13')
    testRuntimeOnly('org.junit.vintage:junit-vintage-engine:5.6.0')
}
```

### TestNG
```gradle
dependencies {
    testImplementation('org.testng:testng:7.1.0')
}
```

## Test execution
Declare the `test` task using either way.
```gradle
test {
    // Your test options here
}
```

```gradle
tasks.withType(Test) {
    // Your test options here
}
```

**[WARN]** Do not forget using Java plugin:<br/>
`apply plugin: 'java'`
{: .notice--warning}

<br/>
Test process is launched via several options on the **Test** task, including the following:
- testLogging {} 
    - events — `Set<String>` — *default:* `[ ]`
    - showStandardStreams — `boolean` — *default:* `false`

    **[SEE]** TestLoggingContainer:<br/>
    [org.gradle.api.tasks.testing.logging.TestLoggingContainer](https://docs.gradle.org/current/javadoc/org/gradle/api/tasks/testing/logging/TestLoggingContainer.html){:target="_blank"}
    {: .notice--info}
    
- useJUnitPlatform {}
    - includeEngines — `Set<String>` — *default:* `[ ]` — *values:* `[junit-vintage, junit-jupiter]`
    - excludeEngines — `Set<String>` — *default:* `[ ]` — *values:* `[junit-vintage, junit-jupiter]`

    **[SEE]** JUnitPlatformOptions:<br/>
    [org.gradle.api.tasks.testing.junitplatform.JUnitPlatformOptions](https://docs.gradle.org/current/javadoc/org/gradle/api/tasks/testing/junitplatform/JUnitPlatformOptions.html){:target="_blank"}
    {: .notice--info}

- useTestNG {}
    - preserveOrder — `boolean` — *default:* `false`
    - useDefaultListeners — `boolean` — *default:* `false`

    **[SEE]** TestNGOptions:<br/>
    [org.gradle.api.tasks.testing.testng.TestNGOptions](https://docs.gradle.org/current/javadoc/org/gradle/api/tasks/testing/testng/TestNGOptions.html){:target="_blank"}
    {: .notice--info}
- filter {}
- debug — `boolean` — *default:* `false`
- ignoreFailures — `boolean` — *default:* `false`
- excludes — `Set<String>` — *default:* `[ ]`
- includes — `Set<String>` — *default:* `[ ]`
- jvmArgs — `List<String>` — *default:* `[ ]`
- allJvmArgs — `List<String>` — *default:* `[ ]`
- bootstrapClasspath — `FileCollection` — *default:* `[ ]`
- classpath — `FileCollection` — *default:* `project.sourceSets.test.runtimeClasspath`
- enableAssertions — `boolean` — *default:* `true`
- environment — `Map<String, Object` — *default:* `environment of the current process`
- executable — `String` — *default:* `java command for the current JVM`
- failFast — `boolean` — *default:* `false`
- forkEvery — `long` — *default:* `0`
- maxHeapSize — `String` — *default:* `null`
- minHeapSize — `String` — *default:* `null`
- maxParallelForks — `int` — *default:* `1`
- scanForTestClasses — `Map<String, Object>` — *default:* `[:]`
- testClassesDirs — `FileCollection` — *default:* `project.sourceSets.test.output.classesDirs`

**[SEE]** Test:<br/>
[org.gradle.api.tasks.testing.Test](https://docs.gradle.org/current/javadoc/org/gradle/api/tasks/testing/Test.html){:target="_blank"}
{: .notice--info}


*[testLogging {}]: Allows to set options related to which test events are logged to the console, and on which detail level.
*[events]: Allows to set options related to which test events are logged to the console, and on which detail level. [STARTED, PASSED, SKIPPED, FAILED, STANDARD_OUT, STANDARD_ERROR]
*[showStandardStreams]: Sets whether output on standard out and standard error will be logged. Equivalent to setting log events {@code TestLogEvent.STANDARD_OUT} and {@code TestLogEvent.STANDARD_ERROR};
*[useJUnitPlatform {}]: Specifies that JUnit Platform (a.k.a. JUnit 5) should be used to execute the tests, configuring JUnit platform specific options. The supplied action configures an instance of JUnitPlatformOptions, which can be used to configure how JUnit platform runs.
*[useTestNG {}]: Specifies that TestNG should be used to execute the tests, configuring TestNG specific options. The supplied closure configures an instance of TestNGOptions, which can be used to configure how TestNG runs.
*[filter {}]: Allows filtering tests for execution

*[allJvmArgs]: The full set of arguments to use to launch the JVM for the process. This includes arguments to define system properties, the minimum/maximum heap size, and the bootstrap classpath.
*[bootstrapClasspath]: The bootstrap classpath to use for the process. The default bootstrap classpath for the JVM is used when this classpath is empty.
*[classpath]: The classpath to use to execute the tests.
*[debug]: Determines whether debugging is enabled for the test process. When enabled — debug = true — the process is started in a suspended state, listening on port 5005. You should disable parallel test execution when debugging and you will need to reattach the debugger occasionally if you use a non-zero value for Test.getForkEvery().
*[enableAssertions]: Returns true if assertions are enabled for the process.
*[environment]: The environment variables to use for the process. Defaults to the environment of this process.
*[excludes]: The exclude patterns for test execution.
*[executable]: The name of the executable to use.
*[failFast]: Indicates if this task will fail on the first failed test.
*[forkEvery]: The maximum number of test classes to execute in a forked test process. The forked test process will be restarted when this limit is reached.
*[ignoreFailures]: Specifies whether the build should break when the verifications performed by this task fail.
*[includes]: The include patterns for test execution.
*[jvmArgs]: The extra arguments to use to launch the JVM for the process. Does not include system properties and the minimum/maximum heap size.
*[maxHeapSize]: The maximum heap size for the process, if any.
*[minHeapSize]: The minimum heap size for the process, if any.
*[maxParallelForks]: The maximum number of test processes to start in parallel.
*[scanForTestClasses]: Specifies whether test classes should be detected. When true the classes which match the include and exclude patterns are scanned for test classes, and any found are executed. When false the classes which match the include and exclude patterns are executed.
*[testClassesDirs]: The directories for the compiled test sources.


## Test filtering
### Using `--tests` option from command line
```bat
--tests {MATCHING_PATTERN}
### OR ###
--tests {'MATCHING_PATTERN'}
```

**[TIP]** MATCHING_PATTERN<br/>
Has apostrophes or not are also OK
{: .notice--info}

1. Test package

    Execute a specific test package (recursively)
    + Package: `com.github.ngoanh2n.scenarios`
    + Class: all test classes in package `com.github.ngoanh2n.scenarios`
    + Method: `any`
    ```bat
    ./gradlew test --tests 'com.github.ngoanh2n.scenarios*'
    ### OR ###
    ./gradlew test --tests 'com.github.ngoanh2n.scenarios.*'
    ```

2. Test class
    - Execute test classes with the specific class name at any test package, with scope:
        + Package: `any`
        + Class: `TestClassName01`
        + Method: `any`
        ```bat
        ./gradlew test --tests TestClassName01
        ### OR ###
        ./gradlew test --tests *TestClassName01
        ```
    - Execute test classes with the containing class name at any test package, with scope:
        + Package: `any`
        + Class: all test classes has name containing `TestClassName`
        + Method: `any`
        ```bat
        ./gradlew test --tests TestClassName*
        ### OR ###
        ./gradlew test --tests *TestClassName*
        ```
    - Execute a test class with the specific class name at specific test package, with scope:
        + Package: `com.github.ngoanh2n.scenarios.childPackage01`
        + Class: `TestClassName01`
        + Method: `any`
        ```bat
        ./gradlew test --tests 'com.github.ngoanh2n.scenarios.childPackage01.TestClassName01'
        ```
    - Execute a test class with the containing class name at specific test package, with scope:
        + Package: `com.github.ngoanh2n.scenarios.childPackage02`
        + Class: `TestClassName01`
        + Method: `any`
        ```bat
        ./gradlew test --tests 'com.github.ngoanh2n.scenarios.childPackage02.TestClassName*'
        ```

3. Test method
    - Execute all test methods in the specific test class
        ```bat
        ### Any package ###
        ./gradlew test --tests TestClassName01.*

        ### Specific package ###
        ./gradlew test --tests 'com.github.ngoanh2n.scenarios.childPackage02.TestClassName01.*'
        ```
    - Execute a specific method name in the specific test class
        ```bat
        ### Any package ###
        ./gradlew test --tests TestClassName01.method01

        ### Specific package ###
        ./gradlew test --tests 'com.github.ngoanh2n.scenarios.childPackage02.TestClassName01.method01'
        ```
    - Execute the second iteration of the specific test class
        ```bat
        ./gradlew test --tests TestClassName01.*[2]
        ```

### Using build script
```gradle
tasks.withType(Test) {
    filter {
        includeTestsMatching "MATCHING_PATTERN"
    }
}
```

## Associate with JUnit5
```gradle
tasks.withType(Test) {
    /*
    * Tell with Gradle that use JUnit5 framework. Default is JUnit
    */
    useJUnitPlatform() {
        /*
        * Filter by engines
        */
        includeEngines 'junit-jupiter'
        //excludeEngines 'junit-vintage'

        /*
        * Filter by tags
        */
        //includeTags 'fast', 'smoke'
        //excludeTags 'slow', 'ci'
    }

    /*
    * Make failing tests do not fail the task
    */
    ignoreFailures = true
    
    testLogging {
        /*
        *  Want to display the following test events
        */
        events 'passed', 'skipped', 'failed'

        /*
        * To show standard out and standard error of the test JVM(s) on the console
        */
        showStandardStreams = true
    }

    /*
    * If any upToDateWhen spec returns false, the task is considered out of date.
    * If they return true, Gradle does the normal behavior of checking input/output files.
    */
    outputs.upToDateWhen { false }

    /*
    * When the JVM starts, it uses the JVMs platform encoding
    */
    systemProperty('file.encoding', encoding)
}
```

## Associate with TestNG
```gradle
tasks.withType(Test) {
    /*
    * Tell with Gradle that use TestNG framework. Default is JUnit
    */
    useTestNG() {
        /*
        * Preserving order of TestNG tests
        */
        preserveOrder true

        /*
        * Grouping TestNG tests by instances
        */
        groupByInstances = true

        /*
        * To generate reports by TestNG library
        */
        useDefaultListeners = false

        /*
        * Set TestNG output dir
        */
        outputDirectory = file('build/testngOutput')

        //includeGroups 'unitTests'
        //excludeGroups 'integrationTests'
    }

    /*
    * Make failing tests do not fail the task
    */
    ignoreFailures = true

    testLogging {
        /*
        *  Want to display the following test events
        */
        events 'passed', 'skipped', 'failed'

        /*
        * To show standard out and standard error of the test JVM(s) on the console
        */
        showStandardStreams = true
    }

    /*
    * Turn off Gradle's HTML report to avoid replacing the reports generated by TestNG library
    */
    reports.html.enabled = false

    /*
    * If any upToDateWhen spec returns false, the task is considered out of date.
    * If they return true, Gradle does the normal behavior of checking input/output files.
    */
    outputs.upToDateWhen { false }

    /*
    * When the JVM starts, it uses the JVMs platform encoding
    */
    systemProperty('file.encoding', encoding)
}
```

**[SOURCE]** Source code illustrates on Github:<br/>
JUnit5 with Gradle: See or clone [run-junit5-tests-with-gradle](https://github.com/ngoanh2n/blog-demonstrations/tree/master/run-junit5-tests-with-gradle){:target="_blank"}<br/>
TestNG with Gradle: See or clone [run-testng-tests-with-gradle](https://github.com/ngoanh2n/blog-demonstrations/tree/master/run-testng-tests-with-gradle){:target="_blank"}
{: .notice--success}

**[REFERENCES]** Testing in Java & JVM projects:<br/>
[https://docs.gradle.org/current/userguide/java_testing.html](https://docs.gradle.org/current/userguide/java_testing.html){:target="_blank"}
{: .notice--info}
