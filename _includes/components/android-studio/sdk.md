<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/sdk.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/android-studio#sdk" %}


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
>> Prerequisites
>>
>> Open `Android Studio`
>
> {: .note-title .text-epsilon }
>> ✅ `Welcome` Window
>>
>> Click `Next`
>
> {: .note-title .text-epsilon }
>> ✅ `Install Type` Window
>>
>> 1. Select `Custom`
>> 2. Click `Next`
>
> {: .note-title .text-epsilon }
>> ✅ `SDK Components Setup` Window
>>
>> Click `Next`
>
> {: .note-title .text-epsilon }
>> ✅ `Emulator Settings` Window
>>
>> Click `Next`
>
>{: .note-title .text-epsilon }
>> ✅ `Installing Android Emulator hypervisor driver` Window
>>
>> Click `Next`
>
> {: .note-title .text-epsilon }
>> ✅ `Verify Settings` Window
>>
>> Click `Next`
>
> {: .note-title .text-epsilon }
>> ✅ `License Agreement` Window
>>
>> 1. Select `Accept` for all licenses
>> 2. Click `Finish`
>
> {: .note-title .text-epsilon }
>> ✅ `Downloading Components` Window
>>
>> Click `Finish`
