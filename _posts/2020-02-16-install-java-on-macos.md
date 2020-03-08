---
title:  "Install Java on macOS"
modified: 2020-02-18T21:00:00+07:00
permalink: /how-to/install-java-on-macos
categories: 
  - How To
  - Setup Environment
tags:
  - Java
  - macOS
  - Homebrew
---

Java is a programming language and computing platform first released by Sun Microsystems in 1995. There are lots of applications and websites that will not work unless you have Java installed, and more are created every day. Java is fast, secure, and reliable. From laptops to datacenters, game consoles to scientific supercomputers, cell phones to the Internet, Java is everywhere!

{% include base_path %}
{% include toc title="Table of Contents" %}

## Install through Homebrew
1. [Install Homebrew]({{ site.baseurl }}/how-to/install-homebrew-on-macos)

2. Add the casks tap<br/>
Type the following command in your terminal.

    ```bat
    brew tap homebrew/cask-versions
    ```
    And for the [AdoptOpenJDK](https://github.com/AdoptOpenJDK/homebrew-openjdk) versions<br/>
    ```bat
    brew tap adoptopenjdk/openjdk
    ```
    These casks change their Java versions often, and there might be other taps out there with additional Java versions.

3. Look for installable versions

    ```bat
    brew search java
    ```
    And for [AdoptOpenJDK](https://github.com/AdoptOpenJDK/homebrew-openjdk) versions
    ```bat
    brew search jdk
    ```

4. Check the details on the version that will be installed

    ```bat
    brew cask info java
    ```
    And for [AdoptOpenJDK](https://github.com/AdoptOpenJDK/homebrew-openjdk) versions
    ```bat
    brew cask info adoptopenjdk
    ```

5. Install a specific version of the JDK<br/>
Old:
    ```bat
    ## for latest ##
    brew cask install java

    ## for Java 8 ##
    brew cask install java8
    ```
New:
    ```bat
    brew cask install adoptopenjdk8
    brew cask install adoptopenjdk9
    brew cask install adoptopenjdk10
    brew cask install adoptopenjdk11
    ```

## Set JAVA_HOME
### Confirm installation succeeded
Type the following command in your terminal.
```bat
/usr/libexec/java_home -V
```
```console
Ngoans-Mac:blog ngoanh2n$ /usr/libexec/java_home -V
Matching Java Virtual Machines (1):
    1.8.0_211, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_211.jdk/Contents/Home

/Library/Java/JavaVirtualMachines/jdk1.8.0_211.jdk/Contents/Home
```

### Set through `.bash_profile`
1. Open `.bash_profile` using *nano*

    ```bat
    sudo nano ~/.bash_profile
    ```

2. Export JAVA_HOME by Java instalation path<br/>
Copy and paste into editing `.bash_profile` window

    ```bash
    export JAVA_HOME=$(/usr/libexec/java_home)
    ```

    > **[TIP]** Export a specific version<br/>
    > ```bash
    >  export JAVA_HOME=$(/usr/libexec/java_home -v X.X.X)
    >  ```
    {: .notice--info}

    Press `Y` to save changes and press `CTRL+X` to exit the bash.

3. Reload `.bash_profile`

    ```bat
    source ~/.bash_profile
    ```

4. Confirm JAVA_HOME

    ```bat
    java -version
    ```
    ```console
    Ngoans-Mac:blog ngoanh2n$ java -version
    java version "1.8.0_211"
    Java(TM) SE Runtime Environment (build 1.8.0_211-b12)
    Java HotSpot(TM) 64-Bit Server VM (build 25.211-b12, mixed mode)
    ```

**[REFERENCES]** Stackoverflow:<br/>
[Question 52524112](https://stackoverflow.com/questions/52524112/how-do-i-install-java-on-mac-osx-allowing-version-switching){:target="_blank"}
{: .notice--info}
