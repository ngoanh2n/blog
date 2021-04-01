---
published: false
title:  "Install Homebrew on macOS"
modified: 2020-02-18T21:00:00+07:00
permalink: /how-to/install-homebrew-on-macos
categories: 
  - Setup Environment
  - How To
tags:
  - Homebrew
  - macOS
---

Homebrew is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system and Linux.

{% include base_path %}
{% include toc title="Table of Contents" %}

## Install Homebrew
The simplest way to install Homebrew is through ruby and curl, accomplished with a single command.

- Open the `Terminal` application in `/Applications/Utilities/`
- Copy and paste below command into the terminal window.

    ```bat
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```

<figure class='half_center'>
	<a href="{{ site.baseurl }}/images/20200216/install-homebrew.png"><img src="{{ site.baseurl }}/images/20200216/install-homebrew.png"></a>
	<figcaption>What you can see after runned command.</figcaption>
</figure>

To check the version type by the following command:
```console
Ngoans-Mac:~ ngoanh2n$ brew -v
Homebrew 2.2.5
Homebrew/homebrew-core (git revision 948e; last commit 2020-02-16)
Homebrew/homebrew-cask (git revision c718d; last commit 2020-02-16)
```

**[TIP] Show helping document:**<br/>
`brew help`<br/>
{: .notice--success}

## Install Software Packages through Homebrew
Install packages with Homebrew by the following command:
```bat
brew install [package name]
```
For example:
```bat
brew install wget
```

## Uninstall Homebrew
Uninstall Homebrew is through ruby and curl with a single command.
```bat
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```
