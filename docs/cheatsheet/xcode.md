---
layout: default
nav_order: 1
parent: Cheatsheet
title: Xcode
---

{% include components/title.md value="macOS Cheatsheet" %}
{% include components/toc.md %}

---

### Check Version Of Xcode Select

{: .note-title .text-epsilon }
>
> ```shell
> xcode-select --version
> ```

### Check If Xcode Is Installed

{: .note-title .text-epsilon }
>
> ```shell
> xcode-select --print-path
> ```

### Install Command Line Tools (CLT)

{: .note-title .text-epsilon } 
>
> 1. Open dialog for installation of the command line developer tools
> ```shell
> xcode-select --install
> ```
> 2. Click `Install`
> 3. Click `Argree`
> 4. Wait for `Downloading software`
>
> <hr>{: .zone-hr }
>
> {: .note-title .text-epsilon } 
>> 🔲 Validation
>>
>> ```shell
>> xcode-select --print-path
>> ```
>
> {: .note-title .text-epsilon } 
>> ℹ️ Location
>>
>> `/Library/Developer/CommandLineTools`
