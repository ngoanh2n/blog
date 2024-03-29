<!-- LOCATION -->
<!-- _includes/components/intellij-idea/ -->

<!-- INCLUDE -->
<!-- components/intellij-idea/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference             = "/env/intellij-idea" %}
{% assign download_link_macos   = "https://www.jetbrains.com/idea/download/?section=mac" %}
{% assign file_download_macos   = "ideaIC-XXX.X.X.dmg" %}
{% assign download_link_windows = "https://www.jetbrains.com/idea/download/?section=windows" %}
{% assign file_download_windows = "ideaIC-XXX.X.X.exe" %}


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
> 1. Visit [{{ download_link_macos }}]({{ download_link_macos }}){:target="\_blank"}
> 2. Click `Download` at `IntelliJ IDEA Community Edition`
> 3. Open `{{ file_download_macos }}` in `Downloads`
> 4. Drag `IntelliJ IDEA CE` to the `Applications`
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
>> choco install intellijidea-community
>> ```
>>
>> {: .warning }
>> Open `Command Prompt` with administrator privileges
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>>
>> 1. Visit [{{ download_link_windows }}]({{ download_link_windows }}){:target="\_blank"}
>> 2. Click `Download` at `IntelliJ IDEA Community Edition` section
>> 3. Open `{{ file_download_windows }}` in `Downloads`
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
>> 1. Visit [{{ download_link_macos }}]({{ download_link_macos }}){:target="\_blank"}
>> 2. Click `Download` at `IntelliJ IDEA Community Edition`
>> 3. Open `{{ file_download_macos }}` in `Downloads`
>> 4. Drag `IntelliJ IDEA CE` to the `Applications`
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> {: .note-title .text-epsilon }
>>> 🔘 Chocolatey
>>>
>>> ```shell
>>> choco install intellijidea-community
>>> ```
>>>
>>> {: .warning }
>>> Open `Command Prompt` with administrator privileges
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Setup Wizard
>>>
>>> 1. Visit [{{ download_link_windows }}]({{ download_link_windows }}){:target="\_blank"}
>>> 2. Click `Download` at `IntelliJ IDEA Community Edition` section
>>> 3. Open `{{ file_download_windows }}` in `Downloads`
>>> 4. Do installation procedures of Setup Wizard
{% endif %}
