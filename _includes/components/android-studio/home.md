<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/home.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference            = "/env/android-studio#android-home" %}
{% assign sdk_location_macos   = "/Users/{USER}/Library/Android/sdk" %}
{% assign sdk_location_windows = "C:\Users\{USER}\AppData\Local\sdk" %}


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

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> By default, SDK location is `{{ sdk_location_macos }}`.<br>
> Run the following commands in Terminal:
> ```shell
> echo "export ANDROID_HOME={{ sdk_location_macos }}" >> ~/.zshrc
> echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.zshrc
> echo "export PATH=\$PATH:\$ANDROID_HOME/tools" >> ~/.zshrc
> ```
>
> {: .warning }
> Replace `{USER}` by your current username!
{% endif %}

<!-- Windows -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> By default, SDK location is `{{ sdk_location_windows }}`.<br>
> 1. Open `Command Prompt` with administrator
> 2. Run a command
> 3. Close `Command Prompt`
>
> Repeat the above process for each command in Command Prompt:
> ```shell
> setx ANDROID_HOME "{{ sdk_location_windows }}"
> setx PATH "%PATH%;%ANDROID_HOME%\platform-tools";
> setx PATH "%PATH%;%ANDROID_HOME%\tools";
> ```
>
> {: .warning }
> Replace `{USER}` by your current username!
{% endif %}

<!-- All -->
{% if platform == nil %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>>
>> By default, SDK location is `{{ sdk_location_macos }}`.<br>
>> Run the following commands in Terminal:
>> ```shell
>> echo "export ANDROID_HOME={{ sdk_location_macos }}" >> ~/.zshrc
>> echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.zshrc
>> echo "export PATH=\$PATH:\$ANDROID_HOME/tools" >> ~/.zshrc
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>>
>> By default, SDK location is `{{ sdk_location_windows }}`.<br>
>> 1. Open `Command Prompt` with administrator
>> 2. Run a command
>> 3. Close `Command Prompt`
>>
>> Repeat the above process for each command in Command Prompt:
>> ```shell
>> setx ANDROID_HOME "{{ sdk_location_windows }}"
>> setx PATH "%PATH%;%ANDROID_HOME%\platform-tools";
>> setx PATH "%PATH%;%ANDROID_HOME%\tools";
>> ```
>
> {: .warning }
> Replace `{USER}` by your current username!
{% endif %}
