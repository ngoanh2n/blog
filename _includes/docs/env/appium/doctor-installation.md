<!-- _includes/docs/env/appium/ -->

{% assign platform = include.platform %}

{% assign stm_xcuitest =  "`$ appium driver doctor xcuitest`" %}
{% assign stm_uiautomator2 =  "`$ appium driver doctor uiautomator2`" %}

<!-- macOS & Windows -->
{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> 🔲 Installation
>
> - {{stm_xcuitest}}
> - {{stm_uiautomator2}}

<!-- Windows -->
{% else %}
{: .note-title .text-epsilon }
> 🔲 Installation
>
> - {{stm_uiautomator2}}
{% endif %}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> 🔲 Installation
> 
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> - {{stm_xcuitest}}
>> - {{stm_uiautomator2}}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> - {{stm_uiautomator2}}
{% endif %}
