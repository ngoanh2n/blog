<!-- LOCATION -->
<!-- _includes/docs/env/git/ -->

<!-- INCLUDE -->
<!-- docs/env/git/installation.md -->

<!-- VARIABLE -->
<!-- platform: [macos, windows], default to ALL -->
<!-- required: [true, false], default to true -->

{% assign platform = include.platform %}
{% assign required = include.required %}

{% assign stm_macos =  "brew install git" %}
{% assign stm_windows =  "choco install git -y" %}

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
> ```shell
> {{stm}}
> ```

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> ```shell
>> {{stm_macos}}
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> ```shell
>> {{stm_windows}}
>> ```
{% endif %}
