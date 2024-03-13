<!-- _includes/docs/env/intellij-idea/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/intellij-idea/location.md  -->
<!-- 2. include docs/env/intellij-idea/location.md platform="macos" -->
<!-- 3. include docs/env/intellij-idea/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "https://www.jetbrains.com/idea/download/?section=mac" %}
{% assign stm_windows =  "https://www.jetbrains.com/idea/download/?section=windows" %}

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
> [{{stm}}]({{stm}}){:target="\_blank"}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> ✅ Installation
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> [{{stm_macos}}]({{stm_macos}}){:target="\_blank"}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> [{{stm_windows}}]({{stm_windows}}){:target="\_blank"}
{% endif %}
