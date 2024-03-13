---
layout: default
nav_order: 1
parent: Cheatsheet
title: macOS
---

# macOS Cheatsheet
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
---

{% include components/note.md %}

### Java

{: .note-title .text-epsilon }
> 🔲 Switch To Version
>
> {: .note-title .text-epsilon }
>> ✅ Open `.zshrc `file
>>
>> `$ nano ~/.zshrc`
>
> {: .note-title .text-epsilon }
>> ✅ Change desired value of `-v` at below row
>>
>> {: .highlight :}
>> For example, I switch to Java 11!
>>
>> `$ export JAVA_HOME=$(/usr/libexec/java_home -v 11)`

{: .note-title .text-epsilon }
> 🔲 Show JAVA_HOME
>
> `$ /usr/libexec/java_home`

{: .note-title .text-epsilon }
> 🔲 Show All Version Paths
>
> `$ /usr/libexec/java_home -V`

{: .note-title .text-epsilon }
> 🔲 Remove All Versions
>
> `$ sudo rm -fr /Library/Java/JavaVirtualMachines/jdk-{VERSION}.jdk/`<br>
> `$ sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin`<br>
> `$ sudo rm -fr /Library/PreferencePanes/JavaControlPanel.prefPane`
