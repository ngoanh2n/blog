<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/inspector-installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference              = "/env/appium#inspector" %}
{% assign file_download_macos    = "Appium-Inspector-mac-xxxx.x.x.dmg" %}
{% assign file_download_windows  = "Appium-Inspector-windows-xxxx.x.x-xxx.exe" %}
{% assign link_appiumpro         = "https://appiumpro.com" %}
{% assign link_inspector         = "https://inspector.appiumpro.com" %}
{% assign link_download          = "https://github.com/appium/appium-inspector/releases" %}


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
> Appium Inspector is released in two formats:
> 
> {: .note-title .text-epsilon } 
>> 🔘 Desktop application
>>
>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>> 2. Click `{{ file_download_macos }}`
>> 3. Open the `{{ file_download_macos }}` in `Downloads`
>> 4. Drag `Appium Inspector` and drop to `Applications`
> 
> {: .note-title .text-epsilon } 
>> 🔘 Web application
>>
>> Appium Inspector is hosted by [Appium Pro]({{ link_appiumpro }}){:target="\_blank"}.
>> You can inspect your app on this site directly at [{{ link_inspector }}]({{ link_inspector }}){:target="\_blank"}.
{% endif %}

<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> {{ title }}
> 
> Appium Inspector is released in two formats:
> 
> {: .note-title .text-epsilon } 
>> 🔘 Desktop application
>>
>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>> 2. Click `{{ file_download_windows }}`
>> 3. Open `{{ file_download_windows }}` in `Downloads`
>> 4. Do installation procedures of Setup Wizard
> 
> {: .note-title .text-epsilon } 
>> 🔘 Web application
>>
>> Appium Inspector is hosted by [Appium Pro]({{ link_appiumpro }}){:target="\_blank"}.
>> You can inspect your app on this site directly at [{{ link_inspector }}]({{ link_inspector }}){:target="\_blank"}.
{% endif %}

<!-- PLATFORMS -->
{% if platform == nil %}
{: .note-title .text-epsilon }
> {{ title }}
> 
> Appium Inspector is released in two formats:
> 
> {: .note-title .text-epsilon } 
>> 🔘 Desktop application
>>
>> {: .note-title .text-epsilon }
>>> 🔘 macOS
>>>
>>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>>> 2. Click `{{ file_download_macos }}`
>>> 3. Open `{{ file_download_macos }}` in `Downloads`
>>> 4. Drag `Appium Inspector` to the `Applications`
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Windows
>>>
>>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>>> 2. Click `{{ file_download_windows }}`
>>> 3. Open `{{ file_download_windows }}` in `Downloads`
>>> 4. Do installation procedures of Setup Wizard
> 
> {: .note-title .text-epsilon } 
>> 🔘 Web application
>>
>> Appium Inspector is hosted by [Appium Pro]({{ link_appiumpro }}){:target="\_blank"}.
>> You can inspect your app on this site directly at [{{ link_inspector }}]({{ link_inspector }}){:target="\_blank"}.
{% endif %}