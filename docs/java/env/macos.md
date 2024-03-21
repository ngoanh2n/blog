---
layout: default
nav_order: 1
grand_parent: Java
parent: Environment
title: macOS
---

{% include components/title.md value="Install Environment on macOS" %}
{% include components/toc.md %}
{% include components/note.md %}

---

<!-- General -->
{% include components/title.md level="#" value="General" %}

<!-- Homebrew -->
{% include components/title.md level="##" value="Homebrew" %}
{% include components/homebrew/installation.md referenced=true %}

<!-- Java -->
{% include components/title.md level="##" value="Java" %}

{% include components/title.md level="###" value="JDK" anchor="java-jdk" %}
{% include components/java/jdk-macos.md referenced=true %}

{% include components/title.md level="###" value="Java Home" anchor="java-home" %}
{% include components/java/home-macos.md  referenced=true %}

<!-- Git -->
{% include components/title.md level="##" value="Git" %}
{% include components/git/installation.md platform="macos" referenced=true %}

<!-- IntelliJ IDEA Community Edition -->
{% include components/title.md level="##" value="IntelliJ IDEA Community Edition" anchor="intellij-idea" %}
{% include components/intellij-idea/installation.md platform="macos" referenced=true %}

<!-- NodeJS -->
{% include components/title.md level="##" value="NodeJS" %}
{% include components/nodejs/installation-macos.md required=false referenced=true %}

<!-- Allure Commandline -->
{% include components/title.md level="##" value="Allure Commandline" %}
{% include components/allure-commandline/installation.md platform="macos" required=false referenced=true %}

<!-- GitHub Desktop -->
{% include components/title.md level="##" value="GitHub Desktop" %}
{% include components/github-desktop/installation.md platform="macos" required=false referenced=true %}


<!-- Advance -->
{% include components/title.md level="#" value="Advance" %}

<!-- Xcode -->
{% include components/title.md level="##" value="Xcode" %}

{% include components/title.md level="###" value="IDE" anchor="xcode-ide" %}
{% include components/xcode/ide.md %}

{% include components/title.md level="###" value="SDK" anchor="xcode-sdk" %}
{% include components/xcode/sdk.md %}

{% include components/title.md level="###" value="Simulator" anchor="xcode-simulator" %}
{% include components/xcode/simulator.md %}

<!-- Android Studio -->
{% include components/title.md level="##" value="Android Studio" %}

{% include components/title.md level="###" value="IDE" anchor="android-ide" %}
{% include components/android-studio/ide-macos.md referenced=true %}

{% include components/title.md level="###" value="SDK" anchor="android-sdk" %}
{% include components/android-studio/sdk.md platform="macos" referenced=true %}

{% include components/title.md level="###" value="Emulator" anchor="android-emulator" %}
{% include components/android-studio/emulator.md referenced=true %}

{% include components/title.md level="###" value="Android Home" anchor="android-home" %}
{% include components/android-studio/home-macos.md  referenced=true %}

<!-- Appium -->
{% include components/title.md level="##" value="Appium" %}

{% include components/title.md level="###" value="Server" anchor="appium-server" %}
{% include components/appium/server-installation.md platform="macos" referenced=true %}

{% include components/title.md level="###" value="Driver" anchor="appium-driver" %}
{% include components/appium/driver-installation-macos.md referenced=true %}

{% include components/title.md level="###" value="Plugin" anchor="appium-plugin" %}
{% include components/appium/plugin-installation.md required=false referenced=true %}

{% include components/title.md level="###" value="Inspector" anchor="appium-inspector" %}
{% include components/appium/inspector-installation.md platform="macos" referenced=true %}
