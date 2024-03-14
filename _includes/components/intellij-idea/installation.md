<!-- LOCATION -->
<!-- _includes/components/intellij-idea/ -->

<!-- INCLUDE -->
<!-- components/intellij-idea/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}
{% assign required = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign download_link_macos =  "https://www.jetbrains.com/idea/download/?section=mac" %}
{% assign download_link_windows =  "https://www.jetbrains.com/idea/download/?section=windows" %}

<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path="/env/intellij-idea" %}
{% endif %}


<!-- MAIN CONTENT -->

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign download_link =  download_link_macos %}
    {% else %}
        {% assign download_link =  download_link_windows %}
    {% endif %}

{: .note-title .text-epsilon } 
> {{ title }}
>
> [{{ download_link }}]({{ download_link }}){:target="\_blank"}

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> [{{ download_link_macos }}]({{ download_link_macos }}){:target="\_blank"}
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> [{{ download_link_windows }}]({{ download_link_windows }}){:target="\_blank"}
{% endif %}
