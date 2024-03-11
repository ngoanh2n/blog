<!-- _includes/docs/env/appium/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/appium/location.md  -->
<!-- 2. include docs/env/appium/location.md platform="macos" -->
<!-- 3. include docs/env/appium/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "`/Users/{USER}/.appium/`" %}
{% assign stm_windows =  "`TODO`" %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign stm =  stm_macos %}
    {% else %}
        {% assign stm =  stm_windows %}
    {% endif %}

{: .note-title .text-epsilon }
> ℹ️ Location
>
> {{stm}}

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
