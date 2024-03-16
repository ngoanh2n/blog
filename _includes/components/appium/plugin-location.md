<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/plugin-location.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->

<!-- READ VARIABLES -->
{% assign platform = include.platform %}


<!-- ASSIGN CONSTANTS -->
{% assign stm_macos   =  "`/Users/{USER}/.appium/node_modules/@appium/{installation_key}-plugin`" %}
{% assign stm_windows =  "`C:/Users/{USER}/.appium/node_modules/@appium/{installation_key}-plugin`" %}


<!-- MAIN CONTENT -->

{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{stm_macos}}

<!-- Windows -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{stm_windows}}
{% endif %}

<!-- All -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> {{stm_macos}}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> {{stm_windows}}
{% endif %}
