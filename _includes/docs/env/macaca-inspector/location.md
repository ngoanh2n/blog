<!-- _includes/docs/env/macaca-inspector/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/macaca-inspector/location.md  -->
<!-- 2. include docs/env/macaca-inspector/location.md platform="macos" -->
<!-- 3. include docs/env/macaca-inspector/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "`/usr/local/lib/node_modules/app-inspector/`" %}
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
