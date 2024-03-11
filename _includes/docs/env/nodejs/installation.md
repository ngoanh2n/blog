<!-- _includes/docs/env/nodejs/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/nodejs/location.md  -->
<!-- 2. include docs/env/nodejs/location.md platform="macos" -->
<!-- 3. include docs/env/nodejs/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "`brew install node@20`" %}
{% assign stm_windows =  "`TODO`" %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign stm =  stm_macos %}
    {% else %}
        {% assign stm =  stm_windows %}
    {% endif %}

{: .note-title .text-epsilon }
> ✅ Installation
>
> {{stm}}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> ✅ Installation
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
