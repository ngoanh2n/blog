---
layout: default
nav_order: 2
parent: Cheatsheet
title: Xcode
---

{% include components/title.md value="macOS Cheatsheet" %}
{% include components/toc.md %}

---

## Xcode

##### Check version

{: .note-title .text-epsilon }
>
> ```shell
> xcodebuild -version
> ```

## Xcode Select

##### Check version

{: .note-title .text-epsilon }
>
> ```shell
> xcode-select --version
> ```

##### Check selected directory

{: .note-title .text-epsilon }
>
> ```shell
> xcode-select --print-path
> ```

##### Install Command Line Tools

{: .note-title .text-epsilon }
>
> 1. Open dialog for installation
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

##### Switch Xcode

{: .note-title .text-epsilon }
>
> ```shell
> sudo xcode-select --switch {XCODE_PATH}
> ```
>
> {: .warning}
> Replace dessired `{XCODE_PATH}`<br>
> E.g. `/Applications/Xcode_14.3.1.app`

##### Switch Command Line Tools

{: .note-title .text-epsilon }
>
> ```shell
> sudo xcode-select --switch {DEVELOPER_DIRECTORY}
> ```
>
> {: .warning}
> Replace dessired `{DEVELOPER_DIRECTORY}`<br>
> E.g. `/Library/Developer/CommandLineTools` or `/Applications/Xcode.app/Contents/Developer`

## Simulator

##### Open simulator

{: .note-title .text-epsilon }
>
>```shell
> open -a simulator
>```
> ![](../../../assets/xcode/simulator_04.png)
