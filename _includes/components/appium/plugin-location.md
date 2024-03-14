<!-- _includes/docs/env/appium/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/appium/location.md  -->
<!-- 2. include docs/env/appium/location.md platform="macos" -->
<!-- 3. include docs/env/appium/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos     =  "`/Users/{USER}/.appium/node_modules/@appium/{INSTALLATION_KEY}-plugin`" %}
{% assign stm_windows   =  "`C:/Users/{USER}/.appium/node_modules/@appium/{INSTALLATION_KEY}-plugin`" %}

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
