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
---

{% include components/note.md %}

# General
<hr>{: .head-hr }

{% include components/chocolatey/title.md heading="##" %}
{% include components/chocolatey/installation.md referenced=true %}

{% include components/java/title.md heading="##" %}
{% include components/java/installation-windows.md referenced=true %}

{% include components/git/title.md heading="##" %}
{% include components/git/installation.md platform="windows" referenced=true %}

{% include components/intellij-idea/title.md heading="##" %}
{% include components/intellij-idea/installation.md platform="windows" referenced=true %}

{% include components/nodejs/title.md heading="##" %}
{% include components/nodejs/installation.md platform="windows" required=false referenced=true %}

{% include components/allure-commandline/title.md heading="##" %}
{% include components/allure-commandline/installation.md platform="windows" required=false referenced=true %}

{% include components/github-desktop/title.md heading="##" %}
{% include components/github-desktop/installation.md platform="windows" required=false referenced=true %}

# Advance
<hr>{: .head-hr }

{% include components/appium/title.md heading="##" %}

### Server
{% include components/appium/server-installation.md referenced=true %}

### Driver
{% include components/appium/driver-installation.md referenced=true %}

### Plugin
{% include components/appium/plugin-installation.md required=false referenced=true %}

### Inspector
{% include components/appium/inspector-installation.md referenced=true %}
