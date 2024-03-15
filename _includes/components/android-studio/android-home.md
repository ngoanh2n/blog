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

<!-- ASSIGN CONSTANTS -->
{% assign sdk_location_macos   = "/Users/{USER}/Library/Android/sdk" %}
{% assign sdk_location_windows = "C:\Users\{USER}\AppData\Local\sdk" %}


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

<!-- MACOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> ✅ ANDROID_HOME
>
> {: .note-title .text-epsilon }
>> ℹ️ SDK Location
>>
>> `{{ sdk_location_macos }}` (Default)
>
> {: .note-title .text-epsilon }
>> ✅ Setting
>> 
>> Execute 3 commands in the following, and replace `{USER}` by your current username!
>> ```shell
>> echo "export ANDROID_HOME={{ sdk_location_macos }}" >> ~/.zshrc
>> echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.zshrc
>> echo "export PATH=\$PATH:\$ANDROID_HOME/tools" >> ~/.zshrc
>> ```
{% endif %}

<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> ✅ ANDROID_HOME
>
> {: .note-title .text-epsilon }
>> ℹ️ SDK Location
>>
>> `{{ sdk_location_windows }}` (Default)
>
> {: .note-title .text-epsilon }
>> ✅ Setting
>> 
>> 1. Open `Command Prompt` with administrator
>> 2. Execute a command
>> 3. Close `Command Prompt`
>>
>> Repeat 3 commands in the following, and replace `{USER}` by your current username!
>> ```shell
>> setx ANDROID_HOME "{{ sdk_location_windows }}"
>> setx PATH "%PATH%;%ANDROID_HOME%\platform-tools";
>> setx PATH "%PATH%;%ANDROID_HOME%\tools";
>> ```
{% endif %}

<!-- ALL -->
{% if platform == nil %}
{: .note-title .text-epsilon }
> ✅ ANDROID_HOME
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ SDK Location
>>>
>>> `{{ sdk_location_macos }}` (Default)
>>
>> {: .note-title .text-epsilon }
>>> ✅ Setting
>>> 
>>> Execute 3 commands in the following, and replace `{USER}` by your current username!
>>> ```shell
>>> echo "export ANDROID_HOME={{ sdk_location_macos }}" >> ~/.zshrc
>>> echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.zshrc
>>> echo "export PATH=\$PATH:\$ANDROID_HOME/tools" >> ~/.zshrc
>>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ SDK Location
>>>
>>> `{{ sdk_location_windows }}` (Default)
>>
>> {: .note-title .text-epsilon }
>>> ✅ Setting
>>> 
>>> 1. Open `Command Prompt` with administrator
>>> 2. Execute a command
>>> 3. Close `Command Prompt`
>>>
>>> Repeat 3 commands in the following, and replace `{USER}` by your current username!
>>> ```shell
>>> setx ANDROID_HOME "{{ sdk_location_windows }}"
>>> setx PATH "%PATH%;%ANDROID_HOME%\platform-tools";
>>> setx PATH "%PATH%;%ANDROID_HOME%\tools";
>>> ```
{% endif %}
