<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/ide-windows.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference       = "/env/android-studio#ide-windows" %}
{% assign link_download   = "https://developer.android.com/studio" %}
{% assign download_option = "`Download Android Studio Xxx | xxxx.x.x for Windows`" %}
{% assign file_download   = "`android-studio-xxx.x.x-windows.exe`" %}


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

{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 Chocolatey
>>
>> ```shell
>> choco install androidstudio
>> ```
>>
>> {: .warning }
>> Open `Command Prompt` with administrator privileges
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>>
>> 1. Visit [{{ link_download }}]({{ link_download }}){:target="\_blank"}
>> 2. Click `Download Android Studio Xxx`
>> 3. Check `I have read and agree with the above terms and conditions`
>> 4. Click {{ download_option }}
>> 5. Open {{ file_download }} in `Downloads`
>> 6. Do installation procedures of Setup Wizard
