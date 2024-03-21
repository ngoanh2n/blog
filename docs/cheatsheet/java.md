---
layout: default
nav_order: 2
parent: Cheatsheet
title: Java
---

{% include components/title.md value="macOS Cheatsheet" %}
{% include components/toc.md %}

---

### Switch To Version

{: .note-title .text-epsilon }
>
> 1. Open `~/.zshrc`
> ```shell
> nano ~/.zshrc
> ```
> 2. Change desired version after `-v`
> ```shell
> export JAVA_HOME=$(/usr/libexec/java_home -v 11)
> ```

### Show JAVA_HOME

{: .note-title .text-epsilon }
>
> ```shell
> /usr/libexec/java_home
> ```

### Show All Version Paths

{: .note-title .text-epsilon }
>
> ```shell
> /usr/libexec/java_home -V
> ```

### Remove All Versions

{: .note-title .text-epsilon }
>
> ```shell
> sudo rm -fr /Library/Java/JavaVirtualMachines/jdk-{VERSION}.jdk/
> sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin
> sudo rm -fr /Library/PreferencePanes/JavaControlPanel.prefPane
> ```
