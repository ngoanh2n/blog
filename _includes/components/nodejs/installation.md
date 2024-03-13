<!-- _includes/docs/env/nodejs/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/nodejs/location.md  -->
<!-- 2. include docs/env/nodejs/location.md platform="macos" -->
<!-- 3. include docs/env/nodejs/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "brew install node@20" %}
{% assign stm_windows =  "[https://nodejs.org/en/download](https://nodejs.org/en/download){:target='\_blank'}" %}

<!-- macOS & Windows -->
{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> ✅ Installation
>
> ```shell
> {{stm_macos}}
> ```

<!-- Windows -->
{% else %}
{: .note-title .text-epsilon }
> ✅ Installation
>
> 1. Download by using {{stm_windows}}
> 2. Open the `node-v20.xx.x-xxx.msi` file to install using wizard
{% endif %}

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
>> 1. Download by using {{stm_windows}}
>> 2. Open the `node-v20.xx.x-xxx.msi` file to install using wizard
{% endif %}
