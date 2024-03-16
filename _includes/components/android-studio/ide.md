<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/ide.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference               = "/env/android-studio#ide" %}
{% assign link_download           = "https://developer.android.com/studio" %}
{% assign download_option_macos   = "`Mac with Intel chip` or `Mac with Apple chip`" %}
{% assign download_option_windows = "`Download Android Studio Xxx | xxxx.x.x for Windows`" %}
{% assign file_download_macos     = "`android-studio-xxx.x.x-mac.dmg`" %}
{% assign file_download_windows   = "`android-studio-xxx.x.x-windows.exe`" %}


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

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
> 2. Click `Download Android Studio Xxx`
> 3. Check `I have read and agree with the above terms and conditions`
> 4. Click {{ download_option_macos }}
> 5. Open the {{ file_download_macos }} file in `Downloads`
> 6. Drag `Android Studio` and drop to `Applications`
{% endif %}

<!-- Windows -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 Chocolatey
>>
>> ```shell
>> choco install androidstudio
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>>
>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>> 2. Click `Download Android Studio Xxx`
>> 3. Check `I have read and agree with the above terms and conditions`
>> 4. Click {{ download_option_windows }}
>> 5. Open the {{ file_download_windows }} file in `Downloads`
>> 6. Do installation procedures of Setup Wizard
{% endif %}

<!-- All -->
{% if platform == nil %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>> 2. Click `Download Android Studio Xxx`
>> 3. Check `I have read and agree with the above terms and conditions`
>> 4. Click {{ download_option_macos }}
>> 5. Open the {{ file_download_macos }} file in `Downloads`
>> 6. Drag `Android Studio` and drop to `Applications`
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> {: .note-title .text-epsilon }
>>> 🔘 Chocolatey
>>>
>>> ```shell
>>> choco install androidstudio
>>> ```
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Setup Wizard
>>>
>>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>>> 2. Click `Download Android Studio Xxx`
>>> 3. Check `I have read and agree with the above terms and conditions`
>>> 4. Click {{ download_option_windows }}
>>> 5. Open the {{ file_download_windows }} file in `Downloads`
>>> 6. Do installation procedures of Setup Wizard
{% endif %}
