<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/server-location.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}


<!-- ASSIGN CONSTANTS -->
{% assign location_macos =  "`/Users/{USER}/.appium/`" %}
{% assign location_windows =  "`C:/Users/{USER}/AppData/Roaming/npm/node_modules/appium/`" %}


<!-- MAIN CONTENT -->

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign location =  location_macos %}
    {% else %}
        {% assign location =  location_windows %}
    {% endif %}

{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{ location }}

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
