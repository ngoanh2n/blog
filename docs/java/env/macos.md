---
layout: default
nav_order: 1
grand_parent: Java
parent: Environment
title: macOS
---

# Install Environment on macOS
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

{% include components/note.md %}

---

<!-- General -->
{% include components/title.md heading="#" value="General" %}

<!-- Homebrew -->
{% include components/title.md heading="##" value="Homebrew" %}
{% include components/homebrew/installation.md referenced=true %}

<!-- Java -->
{% include components/title.md heading="##" value="Java" %}

{% include components/title.md heading="###" value="JDK" anchor="java-jdk" %}
{% include components/java/jdk.md platform="macos" referenced=true %}

{% include components/title.md heading="###" value="Java Home" anchor="java-home" %}
{% include components/java/home.md platform="macos" referenced=true %}

<!-- Git -->
{% include components/title.md heading="##" value="Git" %}
{% include components/git/installation.md platform="macos" referenced=true %}

<!-- IntelliJ IDEA Community Edition -->
{% include components/title.md heading="##" value="IntelliJ IDEA Community Edition" anchor="intellij-idea" %}
{% include components/intellij-idea/installation.md platform="macos" referenced=true %}

<!-- NodeJS -->
{% include components/title.md heading="##" value="NodeJS" %}
{% include components/nodejs/installation.md platform="macos" required=false referenced=true %}

<!-- Allure Commandline -->
{% include components/title.md heading="##" value="Allure Commandline" %}
{% include components/allure-commandline/installation.md required=false referenced=true %}

<!-- GitHub Desktop -->
{% include components/title.md heading="##" value="GitHub Desktop" %}
{% include components/github-desktop/installation.md platform="macos" required=false referenced=true %}


<!-- Advance -->
{% include components/title.md heading="#" value="Advance" %}

<!-- Xcode -->
{% include components/title.md heading="##" value="Xcode" %}
{% include components/xcode/installation.md platform="macos" required=false referenced=true %}

<!-- Android Studio -->
{% include components/title.md heading="##" value="Android Studio" %}

{% include components/title.md heading="###" value="IDE" anchor="android-ide" %}
{% include components/android-studio/ide.md platform="macos" referenced=true %}

{% include components/title.md heading="###" value="SDK" anchor="android-sdk" %}
{% include components/android-studio/sdk.md platform="macos" referenced=true %}

{% include components/title.md heading="###" value="Android Home" anchor="android-home" %}
{% include components/android-studio/home.md platform="macos" referenced=true %}

<!-- Appium -->
{% include components/title.md heading="##" value="Appium" %}

{% include components/title.md heading="###" value="Server" anchor="appium-server" %}
{% include components/appium/server-installation.md referenced=true %}

{% include components/title.md heading="###" value="Driver" anchor="appium-server" %}
{% include components/appium/driver-installation.md platform="macos" referenced=true %}

{% include components/title.md heading="###" value="Plugin" anchor="appium-plugin" %}
{% include components/appium/plugin-installation.md required=false referenced=true %}

{% include components/title.md heading="###" value="Inspector" anchor="appium-inspector" %}
{% include components/appium/inspector-installation.md platform="macos" referenced=true %}
