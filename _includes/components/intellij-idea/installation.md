<!-- LOCATION -->
<!-- _includes/docs/env/intellij-idea/ -->

<!-- INCLUDE -->
<!-- docs/env/intellij-idea/installation.md -->

<!-- VARIABLE -->
<!-- platform: [macos, windows], default to ALL -->
<!-- required: [true, false], default to true -->

{% assign platform = include.platform %}
{% assign required = include.required %}

{% assign stm_macos =  "https://www.jetbrains.com/idea/download/?section=mac" %}
{% assign stm_windows =  "https://www.jetbrains.com/idea/download/?section=windows" %}

<!-- Set title -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign stm =  stm_macos %}
    {% else %}
        {% assign stm =  stm_windows %}
    {% endif %}

{: .note-title .text-epsilon } 
> {{ title }}
>
> [{{stm}}]({{stm}}){:target="\_blank"}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
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
