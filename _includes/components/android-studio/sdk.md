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
>> 🔘 Setup Wizard
>> 
>> {: .highlight }
>> When opening for the first time after installed Android Studio.
>>
>> 1. Open `Android Studio`
>> 2. `Welcome` → `Next`
>> 3. `Install Type` → `Next`
>> 4. `SDK Components Setup` → `Next`
>> 5. `Emulator Settings` → `Next`
>> 6. `Installing Android Emulator hypervisor driver` → `Next`
>> 7. `Verify Settings` → `Next`
>> 8. `License Agreement` → `Accept` licenses → `Finish`
>> 9. `Downloading Components` → `Finish`
>
> {: .note-title .text-epsilon }
>> 🔘 Download
>> 
>> {: .highlight }
>> When missing Android SDK Components. That means, you have NOT installed environment yet as above.
>>
>> {: .note-title .text-epsilon }
>>> ✅ SDK Manager
>>>
>>> 1. Open `Android Studio`
>>> 2. Open `Settings`<br>
>>> _Navigation route: `More Actions` > `SDK Manager`_
>>
>> {: .note-title .text-epsilon }
>>> ✅ Settings
>>>
>>> {: .note-title .text-epsilon }
>>>> ✅ SDK Platforms
>>>>
>>>> ☑️ `Show Package Details`<br>
>>>> ☑️ `Android XX.X`<br>
>>>> &nbsp;&nbsp;&nbsp; ☑️ `Android SDK Platform XX`<br>
>>>> &nbsp;&nbsp;&nbsp; ☑️ `Sources for Android XX`
>>> ![](../assets/android-studio/sdk_download_01.png)
>>>
>>> {: .note-title .text-epsilon }
>>>> ✅ SDK Tools
>>>>
>>>> ☑️ `Show Package Details`<br>
>>>> ☑️ `Android SDK Build-Tools XX`<br>
>>>> &nbsp;&nbsp;&nbsp; ☑️ `XX.0.0`<br>
>>>> ☑️ `Android Emulator`<br>
>>>> ☑️ `Android SDK Platform-Tools`
>>> ![](../assets/android-studio/sdk_download_02.png)
