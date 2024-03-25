---
layout: default
nav_order: 2
parent: Cheatsheet
title: Xcode
---

{% include components/title.md value="macOS Cheatsheet" %}
{% include components/toc.md %}

---

## Xcode Select

{: .note-title .text-epsilon }
> Check version of Xcode Select
>
> ```shell
> xcode-select --version
> ```

{: .note-title .text-epsilon }
> Check if Xcode is installed
>
> ```shell
> xcode-select --print-path
> ```

{: .note-title .text-epsilon }
> Install Command Line Tools (CLT)
>
> 1. Open dialog for installation
> ```shell
> xcode-select --print-path
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

## Simulator

{: .note-title .text-epsilon }
> Open simulator
>
>```shell
> open -a simulator
>```
> ![](../../../assets/xcode/simulator_04.png)
