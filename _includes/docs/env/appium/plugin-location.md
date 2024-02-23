<!-- _includes/docs/env/appium/ -->

{% assign platform = include.platform %}

{% assign stm_macos =  "`/Users/{USER}/.appium/node_modules/@appium/images-plugin`" %}
{% assign stm_windows =  "`TODO`" %}

<!-- macOS & Windows -->
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

<!-- ALL -->
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
