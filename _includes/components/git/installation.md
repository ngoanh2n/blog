<!-- LOCATION -->
<!-- _includes/components/git/ -->

<!-- INCLUDE -->
<!-- components/git/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform   = include.platform %}
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference     = "/env/git" %}
{% assign command_brew  = "brew install git" %}
{% assign command_choco = "choco install git -y" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign command =  command_brew %}
    {% else %}
        {% assign command =  command_choco %}
    {% endif %}

{: .note-title .text-epsilon }
> {{ title }}
>
> ```shell
> {{ command }}
> ```

<!-- All -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 macOS
>> 
>> ```shell
>> {{ command_brew }}
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Windows
>> 
>> ```shell
>> {{ command_choco }}
>> ```
{% endif %}
