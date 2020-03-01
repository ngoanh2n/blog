---
title:  "Install IntelliJ IDEA"
modified: 2020-02-18T21:00:00+07:00
permalink: /how-to/install-intellij-idea
categories: 
  - Setup Environment
  - How To
tags:
  - IntelliJ IDEA
  - macOS
  - IntelliJ IDEA Configuration
---

IntelliJ IDEA is an integrated development environment (IDE) written in Java for developing computer software. It is developed by JetBrains, and there are Ultimate and Community editions available. In this post, I'll use `Community edition` - *version 2019.3.3*.

{% include base_path %}
{% include toc title="Table of Contents" %}

## System requirements

|--------|--------|
|**OS version**|10.11 or later for `macOS`, Win 7 SP1 or later for `Windows`|
|**RAM**|2 GB minimum; 8 GB or more recommended for Android development and commercial production|
|**Disk space**|1.5 GB hard disk space + at least 1 GB for caches|
|**JDK version**|JDK 1.8 since 2016|
|**JRE version**|JRE 1.8 is bundled|
|**Screen resolution**|1024×768 minimum screen resolution. 1920×1080 is a recommended screen resolution|

## Downloading
Access [https://www.jetbrains.com/idea/download](https://www.jetbrains.com/idea/download).
It will redirect the URL depending on your OS (Mac, Windows or Linux).

## macOS
- Download the ideaC-20XX.X.X.dmg macOS Disk Image file
- Mount it as another disk in your system
- Copy IntelliJ IDEA to your Applications folder
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/copy-to-application-folder.png"><img src="{{ site.baseurl }}/images/20200217/copy-to-application-folder.png"></a>
    </figure>

## Setup for first time
1. Import Settings
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/setup-import-settings.png"><img src="{{ site.baseurl }}/images/20200217/setup-import-settings.png"></a>
    </figure>

2. Accept JetBrains Privacy Policy
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/setup-agreement.png"><img src="{{ site.baseurl }}/images/20200217/setup-agreement.png"></a>
    </figure>

3. Data Sharing
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/setup-data-sharing.png"><img src="{{ site.baseurl }}/images/20200217/setup-data-sharing.png"></a>
    </figure>

4. Customize IntelliJ IDEA
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/featured-1.png"><img src="{{ site.baseurl }}/images/20200217/featured-1.png"></a>
        <a href="{{ site.baseurl }}/images/20200217/featured-2.png"><img src="{{ site.baseurl }}/images/20200217/featured-2.png"></a>
        <a href="{{ site.baseurl }}/images/20200217/featured-3.png"><img src="{{ site.baseurl }}/images/20200217/featured-3.png"></a>
        <a href="{{ site.baseurl }}/images/20200217/featured-4.png"><img src="{{ site.baseurl }}/images/20200217/featured-4.png"></a>
    </figure>

5. Project Structure
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/structure.png"><img src="{{ site.baseurl }}/images/20200217/structure.png"></a>
    </figure>

    Select SDKs
    <figure class='half'>
        <a href="{{ site.baseurl }}/images/20200217/structure-project-sdk.png"><img src="{{ site.baseurl }}/images/20200217/structure-project-sdk.png"></a>
        <a href="{{ site.baseurl }}/images/20200217/structure-platform-sdk.png"><img src="{{ site.baseurl }}/images/20200217/structure-platform-sdk.png"></a>
    </figure>

## Useful settings
Go to References
<figure class='half'>
    <a href="{{ site.baseurl }}/images/20200217/references.png"><img src="{{ site.baseurl }}/images/20200217/references.png"></a>
</figure>

### Code Completion
<figure class='half'>
    <a href="{{ site.baseurl }}/images/20200217/code-completion.png"><img src="{{ site.baseurl }}/images/20200217/code-completion.png"></a>
</figure>

### Install Plugin - Material Theme UI
Do the following steps in image and restart.
<figure class='half'>
    <a href="{{ site.baseurl }}/images/20200217/install-plugin.png"><img src="{{ site.baseurl }}/images/20200217/install-plugin.png"></a>
</figure>

Material Theme Wizard
<figure class='half'>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-1.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-1.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-2.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-2.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-3.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-3.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-4.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-4.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-5.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-5.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/plugin-theme-6.png"><img src="{{ site.baseurl }}/images/20200217/plugin-theme-6.png"></a>
</figure>


## Gradle project
### Create new project
<figure class='third'>
    <a href="{{ site.baseurl }}/images/20200217/create-gradle-project-1.png"><img src="{{ site.baseurl }}/images/20200217/create-gradle-project-1.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/create-gradle-project-2.png"><img src="{{ site.baseurl }}/images/20200217/create-gradle-project-2.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/create-gradle-project-3.png"><img src="{{ site.baseurl }}/images/20200217/create-gradle-project-3.png"></a>
</figure>

### Import existing project
<figure class='third'>
    <a href="{{ site.baseurl }}/images/20200217/import-gradle-project-1.png"><img src="{{ site.baseurl }}/images/20200217/import-gradle-project-1.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/import-gradle-project-2.png"><img src="{{ site.baseurl }}/images/20200217/import-gradle-project-2.png"></a>
    <a href="{{ site.baseurl }}/images/20200217/import-gradle-project-3.png"><img src="{{ site.baseurl }}/images/20200217/import-gradle-project-3.png"></a>
</figure>
