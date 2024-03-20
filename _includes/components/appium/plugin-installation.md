<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/plugin-installation.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference              = "/env/appium#plugin" %}
{% assign command_install_images = "appium plugin install images" %}
{% assign command_use_images     = "appium --use-plugins=images" %}
{% assign command_list           = "appium plugin list --installed" %}
{% assign location_macos         =  "/Users/{USER}/.appium/node_modules/@appium/images-plugin" %}
{% assign location_windows       =  "C:\Users\{USER}\.appium\node_modules\@appium\images-plugin" %}


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

{% if platform %}
    {% if platform == "macos" %}
        {% assign location = location_macos %}
    {% else %}
        {% assign location = location_windows %}
    {% endif %}

<!-- MACOS || WINDOWS -->

{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔲 Images
>>
>> Plugin for image comparison and finding elements by image.
>> ```shell
>> {{ command_install_images }}
>> ```
>>
>> {: .note-title .text-epsilon }
>>> Usage
>>>
>>> The plugin must be explicitly activated when launching the Appium server.
>>> ```shell
>>> {{ command_use_images }}
>>> ```
>
> <hr>{: .head-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> {{ command_list }}
>> ```
>
>{: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> `{{ location }}`

<!-- PLATFORMS -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔲 Images
>>
>> Plugin for image comparison and finding elements by image.
>> ```shell
>> {{ command_install_images }}
>> ```
>>
>> {: .note-title .text-epsilon }
>>> Usage
>>>
>>> The plugin must be explicitly activated when launching the Appium server.
>>> ```shell
>>> {{ command_use_images }}
>>> ```
>
> <hr>{: .head-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> {{ command_list }}
>> ```
>
>{: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> {: .note-title .text-epsilon }
>>> 🔘 macOS
>>> 
>>> `{{ location_macos }}`
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Windows
>>> 
>> `{{ location_windows }}`
{% endif %}
