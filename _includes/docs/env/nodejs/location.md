<!-- _includes/docs/env/nodejs/ -->

{% assign platform = include.platform %}

{% assign stm_macos_node =  "`/usr/local/lib/node_modules/`" %}
{% assign stm_macos_npm =  "`/usr/local/lib/node_modules/npm/node_modules/`" %}

{% assign stm_windows_node =  "`TODO`" %}
{% assign stm_windows_npm =  "`TODO`" %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign node =  stm_macos_node %}
        {% assign npm =  stm_macos_npm %}
    {% else %}
        {% assign node =  stm_windows_node %}
        {% assign npm =  stm_windows_npm %}
    {% endif %}

{: .note-title .text-epsilon }
> ℹ️ Location
>
> {: .note-title .text-epsilon }
>> ℹ️ Node
>> 
>> {{node}}
>
> {: .note-title .text-epsilon }
>> ℹ️ NPM
>> 
>> {{npm}}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Node
>>>
>>> {{stm_macos_node}}
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ NPM
>>>
>>> {{stm_macos_npm}}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Node
>>>
>>> {{stm_windows_node}}
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ NPM
>>>
>>> {{stm_windows_npm}}
{% endif %}
