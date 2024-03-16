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
{% include components/title.md heading="#" value="General" %}

<!-- Chocolatey -->
{% include components/title.md heading="##" value="Chocolatey" %}
{% include components/chocolatey/installation.md referenced=true %}

<!-- Java -->
{% include components/title.md heading="##" value="Java" %}

{% include components/title.md heading="###" value="JDK" %}
{% include components/java/jdk.md platform="windows" referenced=true %}

{% include components/title.md heading="###" value="Java Home" %}
{% include components/java/java-home.md platform="windows" referenced=true %}

<!-- Git -->
{% include components/title.md heading="##" value="Git" %}
{% include components/git/installation.md platform="windows" referenced=true %}

<!-- IntelliJ IDEA Community Edition -->
{% include components/title.md heading="##" value="IntelliJ IDEA Community Edition" %}
{% include components/intellij-idea/installation.md platform="windows" referenced=true %}

<!-- NodeJS -->
{% include components/title.md heading="##" value="NodeJS" %}
{% include components/nodejs/installation.md platform="windows" required=false referenced=true %}

<!-- Allure Commandline -->
{% include components/title.md heading="##" value="Allure Commandline" %}
{% include components/allure-commandline/installation.md required=false referenced=true %}

<!-- GitHub Desktop -->
{% include components/title.md heading="##" value="GitHub Desktop" %}
{% include components/github-desktop/installation.md platform="windows" required=false referenced=true %}


<!-- Advance -->
{% include components/title.md heading="#" value="Advance" %}

<!-- Android Studio -->
{% include components/title.md heading="##" value="Android Studio" %}

{% include components/title.md heading="###" value="IDE" %}
{% include components/android-studio/ide-installation.md platform="windows" referenced=true %}

{% include components/title.md heading="###" value="Environment" %}
{% include components/android-studio/environment-installation.md platform="windows" referenced=true %}

{% include components/title.md heading="###" value="Android Home" %}
{% include components/android-studio/android-home-setting.md platform="windows" referenced=true %}

<!-- Appium -->
{% include components/title.md heading="##" value="Appium" %}

{% include components/title.md heading="###" value="Server" %}
{% include components/appium/server-installation.md referenced=true %}

{% include components/title.md heading="###" value="Driver" %}
{% include components/appium/driver-installation.md platform="windows" referenced=true %}

{% include components/title.md heading="###" value="Plugin" %}
{% include components/appium/plugin-installation.md required=false referenced=true %}

{% include components/title.md heading="###" value="Inspector" %}
{% include components/appium/inspector-installation.md platform="windows" referenced=true %}
