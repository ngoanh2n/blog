<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/sdk-missed.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/android-studio#sdk-missed" %}


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
> 🔲 Download
>
> {: .highlight }
> When missing Android SDK Components. That means, you have NOT installed environment yet as above.
>
> {: .note-title .text-epsilon }
>> ✅ Prerequisites
>>
>> 1. Open `Android Studio`
>> 2. Navigate to `Settings` window by navigating: `Projects` > `More Actions` > `SDK Manager`
>
> {: .note-title .text-epsilon }
>> ✅ Settings
>>
>> You are standing at `Settings` window: `Languages & Frameworks` > `Android SDK`<br>
>> And, select the checkboxes as below:
>>
>> {: .note-title .text-epsilon }
>>> ✅ SDK Platforms
>>>
>>> 1. Select `Show Package Details`
>>> 2. Select the components as below:
>>>     - [x] `Android XX.X`
>>>         + [x] `Android SDK Platform XX`
>>>         + [x] `Sources for Android XX`
>>
>> {: .note-title .text-epsilon }
>>> ✅ SDK Tools
>>>
>>> 1. Select `Show Package Details`
>>> 2. Select the components as below:
>>>     - [x] `Android SDK Build-Tools XX`
>>>         + [x] `XX.0.0`
>>>     - [x] `Android Emulator`
>>>     - [x] `Android SDK Platform-Tools`
