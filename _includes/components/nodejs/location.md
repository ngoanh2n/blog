<!-- LOCATION -->
<!-- _includes/components/nodejs/ -->

<!-- INCLUDE -->
<!-- components/nodejs/location.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}


<!-- ASSIGN CONSTANTS -->
{% assign location_node_macos   =  "`/usr/local/lib/node_modules/`" %}
{% assign location_npm_macos    =  "`/usr/local/lib/node_modules/npm/node_modules/`" %}
{% assign location_node_windows =  "`C:/Program Files/nodejs/`" %}
{% assign location_npm_windows  =  "`C:/Program Files/nodejs/node_modules/npm/`" %}


<!-- MAIN CONTENT -->

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign node =  location_node_macos %}
        {% assign npm =  location_npm_macos %}
    {% else %}
        {% assign node =  location_node_windows %}
        {% assign npm =  location_npm_windows %}
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

<!-- All -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ Location
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>>
>> {{ location_node_macos }}<br>
>> {{ location_npm_macos }}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>>
>> {{ location_node_windows }}<br>
>> {{ location_npm_windows }}
{% endif %}
