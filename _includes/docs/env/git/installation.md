<!-- _includes/docs/env/git/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/git/installation.md  -->
<!-- 2. include docs/env/git/installation.md platform="macos" -->
<!-- 3. include docs/env/git/installation.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "brew install git" %}
{% assign stm_windows =  "choco install git -y" %}

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
