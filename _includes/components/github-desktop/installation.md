<!-- LOCATION -->
<!-- _includes/components/github-desktop/ -->

<!-- INCLUDE -->
<!-- components/github-desktop/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference             = "/env/github-desktop" %}
{% assign command_brew          = "brew install node@20" %}
{% assign command_choco         = "choco install github-desktop" %}
{% assign download_link         = "https://desktop.github.com" %}
{% assign download_file_macos   = "GitHubDesktop-xxx.zip" %}
{% assign download_file_windows = "GitHubDesktopSetup-xxx.exe" %}

<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

<!-- MACOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
> 2. Click `Download for macOS`
> 3. Open the `{{ download_file_macos }}` file in `Downloads` folder
> 4. After unzipped, move `GitHub Desktop` to `Applications` folder
{% endif %}

<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 Chocolatey
>> 
>> ```shell
>> {{ command_choco }}
>> ```
>>
>> {: .warning }
>> Open `Command Prompt` with administrator privileges
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>> 
>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>> 2. Click `Download for Windows`
>> 3. Open the `{{ download_file_windows }}` file in `Downloads`
>> 4. Do installation procedures of Setup Wizard
{% endif %}

<!-- PLATFORMS -->
{% if platform == nil %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>> 2. Click `Download for macOS`
>> 3. Open the `{{ download_file_macos }}` file in `Downloads` folder
>> 4. After unzipped, move `GitHub Desktop` to `Applications` folder
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
>>>
>>> {: .warning }
>>> Open `Command Prompt` with administrator privileges
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Setup Wizard
>>> 
>>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>>> 2. Click `Download for Windows`
>>> 3. Open the `{{ download_file_windows }}` file in `Downloads`
>>> 4. Do installation procedures of Setup Wizard
{% endif %}
