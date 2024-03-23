<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/emulator.md -->

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
    {% assign title = "🔲 Creating" %}
{% else %}
    {% assign title = "✅ Creating" %}
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
>> ✅ Virtual Device Manager
>> 
>> 1. Open `Android Studio`
>> 2. Open `Device Manager`<br>
>> _Navigation route: `More Actions` > `Virtual Device Manager`_
>> ![](../assets/android-studio/emulator_01.png)
>
> {: .note-title .text-epsilon }
>> ✅ Virtual Device Configuration
>> 
>> 1. `Create Virtual Device` ![](../assets/android-studio/emulator_02.png)
>> 2. Select Device > `Next` ![](../assets/android-studio/emulator_03.png)
>> 3. Download System Image: Click _Download_ icon ![](../assets/android-studio/emulator_04.png)
>> 4. Agree License: `Accept` > `Next` ![](../assets/android-studio/emulator_05.png)
>> 5. Complete Requested Actions: `Finish` ![](../assets/android-studio/emulator_06.png)
>> 6. Select System Image > `Next` ![](../assets/android-studio/emulator_07.png)
>> 7. Verify Configuration > `Finish` ![](../assets/android-studio/emulator_08.png)
>> 8. Verify Virtual Devices ![](../assets/android-studio/emulator_09.png)
