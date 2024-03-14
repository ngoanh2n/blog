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
---

{% include components/note.md %}


<!-- General -->
{% include components/title.md heading="#" value="General" %}

<!-- Homebrew -->
{% include components/title.md heading="##" value="Homebrew" %}
{% include components/homebrew/installation.md referenced=true %}

<!-- Java -->
{% include components/title.md heading="##" value="Java" %}
{% include components/java/installation-macos.md referenced=true %}

<!-- Git -->
{% include components/title.md heading="##" value="Git" %}
{% include components/git/installation.md platform="macos" referenced=true %}

<!-- IntelliJ IDEA Community Edition -->
{% include components/title.md heading="##" value="IntelliJ IDEA Community Edition" %}
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

<!-- Appium -->
{% include components/title.md heading="##" value="Appium" %}
{% include components/title.md heading="###" value="Server" %}
{% include components/appium/server-installation.md referenced=true %}
{% include components/title.md heading="###" value="Driver" %}
{% include components/appium/driver-installation.md platform="macos" referenced=true %}
{% include components/title.md heading="###" value="Plugin" %}
{% include components/appium/plugin-installation.md required=false referenced=true %}
{% include components/title.md heading="###" value="Inspector" %}
{% include components/appium/inspector-installation.md platform="macos" referenced=true %}
