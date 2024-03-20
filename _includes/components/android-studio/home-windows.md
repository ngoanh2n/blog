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
> 1. Open `Command Prompt` with administrator privileges
> 2. Run a command
> 3. Close `Command Prompt`
>
> Repeat the above process for each command in Command Prompt:
> ```shell
> setx /m ANDROID_HOME "{{ sdk_location }}"
> setx /m PATH "%PATH%;%ANDROID_HOME%\platform-tools"
> setx /m PATH "%PATH%;%ANDROID_HOME%\tools"
> ```
>
> {: .warning }
> Replace `{USER}` by your current username!
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> ℹ️ Validation
>>
>> ```shell
>> echo %ANDROID_HOME%
>> adb --version
>> ```
