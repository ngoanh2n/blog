<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/environment.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=path_reference %}
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

<!-- COMPONENTS DOWNLOAD -->

{: .note-title .text-epsilon }
> 🔲 Components Download
>
> {: .highlight }
> When missing Android SDK Components. That means, you have NOT installed environment as above.
>
> {: .note-title .text-epsilon }
>> Prerequisites
>>
>> 1. Open `Android Studio`
>> 2. Navigate to `Settings`<br>
>> _Navigation route:_ `Projects` > `More Actions` > `SDK Manager`
>
> {: .note-title .text-epsilon }
>> ✅ `Settings` window
>>
>> _Navigation route:_ `Languages & Frameworks` > `Android SDK`<br>
>> Tick checkboxes in the following:
>>
>> {: .note-title .text-epsilon }
>>> ✅ `SDK Platforms` Tab
>>>
>>> - ✅ `Show Package Details`
>>> - ✅ `Android 14.0`
>>>   - ✅ `Android SDK Platform 34`
>>>   - ✅ `Sources for Android 34`
>>
>> {: .note-title .text-epsilon }
>>> ✅ `SDK Tools` Tab
>>>
>>> - ✅ `Show Package Details`
>>> - ✅ `Android SDK Build-Tools 35`
>>>   - ✅ `34.0.0`
>>> - ✅ `Android Emulator`
>>> - ✅ `Android SDK Platform-Tools`
