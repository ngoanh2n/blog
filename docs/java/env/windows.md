---
layout: default
nav_order: 2
grand_parent: Java
parent: Environment
title: Windows
---

# Install Environment on Windows
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

{% include components/note.md %}

---

<!-- General -->
{% include components/title.md level="#" value="General" %}

<!-- Chocolatey -->
{% include components/title.md level="##" value="Chocolatey" %}
{% include components/chocolatey/installation.md referenced=true %}

<!-- Java -->
{% include components/title.md level="##" value="Java" %}

{% include components/title.md level="###" value="JDK" anchor="java-jdk" %}
{% include components/java/jdk-windows.md referenced=true %}

{% include components/title.md level="###" value="Java Home" anchor="java-home" %}
{% include components/java/home-windows.md  referenced=true %}

<!-- Git -->
{% include components/title.md level="##" value="Git" %}
{% include components/git/installation.md platform="windows" referenced=true %}

<!-- IntelliJ IDEA Community Edition -->
{% include components/title.md level="##" value="IntelliJ IDEA Community Edition" anchor="intellij-idea" %}
{% include components/intellij-idea/installation.md platform="windows" referenced=true %}

<!-- NodeJS -->
{% include components/title.md level="##" value="NodeJS" %}
{% include components/nodejs/installation-windows.md required=false referenced=true %}

<!-- Allure Commandline -->
{% include components/title.md level="##" value="Allure Commandline" %}
{% include components/allure-commandline/installation.md platform="windows" required=false referenced=true %}

<!-- GitHub Desktop -->
{% include components/title.md level="##" value="GitHub Desktop" %}
{% include components/github-desktop/installation.md platform="windows" required=false referenced=true %}


<!-- Advance -->
{% include components/title.md level="#" value="Advance" %}

<!-- Android Studio -->
{% include components/title.md level="##" value="Android Studio" %}

{% include components/title.md level="###" value="IDE" anchor="android-ide" %}
{% include components/android-studio/ide-windows.md referenced=true %}

{% include components/title.md level="###" value="SDK" anchor="android-sdk" %}
{% include components/android-studio/sdk.md platform="windows" referenced=true %}

{% include components/title.md level="###" value="Android Home" anchor="android-home" %}
{% include components/android-studio/home-windows.md  referenced=true %}

<!-- Appium -->
{% include components/title.md level="##" value="Appium" %}

{% include components/title.md level="###" value="Server" anchor="appium-server" %}
{% include components/appium/server-installation.md referenced=true %}

{% include components/title.md level="###" value="Driver" anchor="appium-driver" %}
{% include components/appium/driver-installation-windows.md referenced=true %}

{% include components/title.md level="###" value="Plugin" anchor="appium-plugin" %}
{% include components/appium/plugin-installation.md required=false referenced=true %}

{% include components/title.md level="###" value="Inspector" anchor="appium-inspector" %}
{% include components/appium/inspector-installation.md platform="windows" referenced=true %}
