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

{% include components/homebrew/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/chocolatey" %}
{% include components/homebrew/installation.md %}

{% include components/java/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/java" %}
{% include components/java/installation-macos.md %}

{% include components/git/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/git" %}
{% include components/git/installation.md platform="macos" %}

{% include components/intellij-idea/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/intellij-idea" %}
{% include components/intellij-idea/installation.md platform="macos" %}

{% include components/nodejs/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/nodejs" %}
{% include components/nodejs/installation.md platform="macos" required=false %}

{% include components/allure-commandline/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/allure-commandline" %}
{% include components/allure-commandline/installation.md platform="macos" required=false %}

{% include components/github-desktop/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/github-desktop" %}
{% include components/github-desktop/installation.md platform="macos" required=false %}

# Advance
<hr>{: .head-hr }

{% include components/appium/title.md useMDHead="###" %}
{% include components/reference.md fromPath="/env/appium" %}

#### Server
{% include components/appium/server-installation.md %}

#### Driver
{% include components/appium/driver-installation.md %}

#### Plugin
{% include components/appium/plugin-installation.md required=false %}

#### Inspector
{% include components/appium/inspector-installation.md %}
