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

# General
<hr>{: .head-hr }

{% include components/homebrew/title.md heading="##" %}
{% include components/homebrew/installation.md referenced=true %}

{% include components/java/title.md heading="##" %}
{% include components/java/installation-macos.md referenced=true %}

{% include components/git/title.md heading="##" %}
{% include components/git/installation.md platform="macos" referenced=true %}

{% include components/intellij-idea/title.md heading="##" %}
{% include components/intellij-idea/installation.md platform="macos" referenced=true %}

{% include components/nodejs/title.md heading="##" %}
{% include components/nodejs/installation.md platform="macos" required=false referenced=true %}

{% include components/allure-commandline/title.md heading="##" %}
{% include components/allure-commandline/installation.md platform="macos" required=false referenced=true %}

{% include components/github-desktop/title.md heading="##" %}
{% include components/github-desktop/installation.md platform="macos" required=false referenced=true %}

# Advance
<hr>{: .head-hr }

{% include components/xcode/title.md heading="##" %}
{% include components/xcode/installation.md platform="macos" required=false referenced=true %}

{% include components/appium/title.md heading="##" %}

### Server
{% include components/appium/server-installation.md referenced=true %}

### Driver
{% include components/appium/driver-installation.md referenced=true %}

### Plugin
{% include components/appium/plugin-installation.md required=false referenced=true %}

### Inspector
{% include components/appium/inspector-installation.md referenced=true %}
