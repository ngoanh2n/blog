<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/home-windows.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference    = "/env/android-studio#android-home-windows" %}
{% assign sdk_location = "C:\Users\{USER}\AppData\Local\sdk" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Setting" %}
{% else %}
    {% assign title = "✅ Setting" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon }
> {{ title }}
>
> By default, SDK location is `{{ sdk_location }}`.<br>
> The environment variables that need to be set in the following:
> - `ANDROID_HOME`
> - Tools:
>   - Platform Tools: `adb`
>   - Build Tools: `apksigner`
>   - Command-Line Tools: `avdmanager`, `sdkmanager`, `apkanalyzer`
>   - Emulator: `emulator`, `mksdcard`
> 
> ```shell
> setx /m ANDROID_HOME "{{ sdk_location }}" & refreshenv
> setx /m PATH "%PATH%;%ANDROID_HOME%\platform-tools" & refreshenv
> setx /m PATH "%PATH%;%ANDROID_HOME%\build-tools\{API_LEVEL}" & refreshenv
> setx /m PATH "%PATH%;%ANDROID_HOME%\cmdline-tools\{CMD_TOOLS_VERSION}" & refreshenv
> setx /m PATH "%PATH%;%ANDROID_HOME%\emulator" & refreshenv
> ```
>
> {: .warning }
> ☑️ Open `Command Prompt` with administrator privileges<br>
> ☑️ Replace `{USER}` by your current username<br>
> ☑️ Replace `{API_LEVEL}` (E.g. `34.0.0`)<br>
> ☑️ Replace `{CMD_TOOLS_VERSION}` (E.g. `13.0`)
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> echo %ANDROID_HOME%
>> adb --version
>> ```
