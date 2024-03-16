<!-- LOCATION -->
<!-- _includes/components/java/ -->

<!-- INCLUDE -->
<!-- components/java/java-home.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform = include.platform %}
{% assign required = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/java#java-home" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Setting" %}
{% else %}
    {% assign title = "✅ Setting" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

<!-- MACOS -->
{% if platform == "macos" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔘 Latest Version
>>
>> ```shell
>> echo "export JAVA_HOME=\$(/usr/libexec/java_home)" >> ~/.zshrc
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 Specific Version
>>
>> ```shell
>> echo "export JAVA_HOME=\$(/usr/libexec/java_home -v 17)" >> ~/.zshrc
>> ```
{% endif %}

<!-- WINDOWS -->
{% if platform == "windows" %}
{: .note-title .text-epsilon }
> {{ title }}
>
> ```shell
> setx TODO
> ```
{% endif %}

<!-- ALL -->
{% if platform == nil %}
{: .note-title .text-epsilon } 
> {{ title }}
>
> {: .note-title .text-epsilon } 
>> 🔘 macOS
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Latest Version
>>>
>>> ```shell
>>> echo "export JAVA_HOME=\$(/usr/libexec/java_home)" >> ~/.zshrc
>>> ```
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Specific Version
>>>
>>> ```shell
>>> echo "export JAVA_HOME=\$(/usr/libexec/java_home -v 17)" >> ~/.zshrc
>>> ```
>
> {: .note-title .text-epsilon } 
>> 🔘 Windows
>>
>> ```shell
>> setx TODO
>> ```
{% endif %}
