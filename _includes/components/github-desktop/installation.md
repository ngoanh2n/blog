<!-- LOCATION -->
<!-- _includes/docs/env/github-desktop/ -->

<!-- INCLUDE -->
<!-- docs/env/github-desktop/installation.md -->

<!-- VARIABLE -->
<!-- platform: [macos, windows], default to ALL -->
<!-- required: [true, false], default to true -->

{% assign platform = include.platform %}
{% assign required = include.required %}

{% assign command_brew = "brew install node@20" %}
{% assign command_choco = "choco install github-desktop" %}

{% assign download_link = "https://desktop.github.com" %}
{% assign download_file_macos = "`GitHubDesktop-xxx.zip`" %}
{% assign download_file_windows = "`GitHubDesktopSetup-xxx.exe`" %}

<!-- Set title -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}

<!-- macOS & Windows -->
{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
> 2. Click `Download for macOS`
> 3. Open the {{ download_file_macos }} file in `Downloads` folder
> 4. After unzipped, move `GitHub Desktop` to `Applications` folder

<!-- Windows -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 Chocolatey
>> 
>> ```shell
>> {{ command_choco }}
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>> 
>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>> 2. Click `Download for Windows`
>> 3. Open the {{ download_file_windows }} file in `Downloads`
>> 4. Do installation procedures of Setup Wizard
{% endif %}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>> 2. Click `Download for macOS`
>> 3. Open the {{ download_file_macos }} file in `Downloads` folder
>> 4. After unzipped, move `GitHub Desktop` to `Applications` folder
>
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Chocolatey
>>> 
>>> ```shell
>>> {{ command_choco }}
>>> ```
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Setup Wizard
>>> 
>>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>>> 2. Click `Download for Windows`
>>> 3. Open the {{ download_file_windows }} file in `Downloads`
>>> 4. Do installation procedures of Setup Wizard
{% endif %}
