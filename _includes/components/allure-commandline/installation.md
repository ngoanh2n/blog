<!-- LOCATION -->
<!-- _includes/components/allure-commandline/ -->

<!-- INCLUDE -->
<!-- components/allure-commandline/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference            = "/env/allure-commandline" %}
{% assign command_installation = "npm install allure-commandline --global" %}
{% assign command_validation   = "allure --version" %}
{% assign location_macos       = "`/usr/local/lib/node_modules/allure-commandline`" %}
{% assign location_windows     = "`C:\Users\{USER}\AppData\Roaming\npm\node_modules\allure-commandline`" %}


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
> {{ command_installation }}
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
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> {{ location_macos }}
{% endif %}


<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> ```shell
> {{ command_installation }}
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
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> {{ location_windows }}
{% endif %}


<!-- PLATFORMS -->
{% if platform == nil %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> ```shell
> {{ command_installation }}
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
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> {: .note-title .text-epsilon }
>>> 🔘 macOS
>>> 
>>> {{ location_macos }}
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Windows
>>> 
>>> {{ location_windows }}
{% endif %}
