<!-- LOCATION -->
<!-- _includes/components/nodejs/ -->

<!-- INCLUDE -->
<!-- components/nodejs/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}
{% assign required = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign command_brew = "brew install node@20" %}
{% assign command_choco = "choco install nodejs-lts" %}
{% assign download_link = "https://nodejs.org/en/download" %}
{% assign download_file_windows = "`node-v20.xx.x-xxx.msi`" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path="/env/nodejs" %}
{% endif %}


<!-- MAIN CONTENT -->

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
> ```shell
> {{ command_brew }}
> ```

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
>> 2. Click `Windows Installer`
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
>> ```shell
>> {{ command_brew }}
>> ```
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
>>> 2. Click `Windows Installer`
>>> 3. Open the {{ download_file_windows }} file in `Downloads`
>>> 4. Do installation procedures of Setup Wizard
{% endif %}
