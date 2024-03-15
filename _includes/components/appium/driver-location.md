<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/driver-location.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}


<!-- ASSIGN CONSTANTS -->
{% assign location_macos   =  "`/Users/{USER}/.appium/node_modules/appium-{installation_key}-driver/`" %}
{% assign location_windows =  "`C:/Users/{USER}/.appium/node_modules/appium-{installation_key}-driver`" %}


<!-- MAIN CONTENT -->

<!-- macOS & Windows -->
{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{ location_macos }}

<!-- Windows -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{ location_windows }}
{% endif %}

<!-- All -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> {{ location_macos }}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> {{ location_windows }}
{% endif %}
