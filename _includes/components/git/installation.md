<!-- LOCATION -->
<!-- _includes/components/git/ -->

<!-- INCLUDE -->
<!-- components/git/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference     = "/env/git" %}
{% assign command_installation_macos  = "brew install git" %}
{% assign command_installation_windows = "choco install git" %}
{% assign command_validation   = "git --version" %}


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


<!-- MACOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> ```shell
> {{ command_installation_macos }}
> ```
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> {{ command_validation }}
>> ```
{% endif %}


<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> ```shell
> {{ command_installation_windows }}
> ```
>
> {: .warning }
> Open `Command Prompt` with administrator privileges
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> {{ command_validation }}
>> ```
{% endif %}


<!-- PLATFORMS -->
{% if platform == nil %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> ```shell
>> {{ command_installation_macos }}
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> ```shell
>> {{ command_installation_windows }}
>> ```
>>
>> {: .warning }
>> Open `Command Prompt` with administrator privileges
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> {{ command_validation }}
>> ```
{% endif %}
