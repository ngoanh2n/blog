<!-- LOCATION -->
<!-- _includes/components/android-studio/ -->

<!-- INCLUDE -->
<!-- components/android-studio/sdk-location.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}

<!-- ASSIGN CONSTANTS -->
{% assign sdk_location_macos   = "`/Users/{USER}/Library/Android/sdk/`" %}
{% assign sdk_location_windows = "`C:/Users/{USER}/AppData/Local/sdk/`" %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign sdk_location =  sdk_location_macos %}
    {% else %}
        {% assign sdk_location =  sdk_location_windows %}
    {% endif %}

{: .note-title .text-epsilon }
> ℹ️ SDK Location
>
> {{sdk_location}}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> ℹ️ SDK Location
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> {{sdk_location_macos}}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> {{sdk_location_windows}}
{% endif %}
