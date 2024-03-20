<!-- LOCATION -->
<!-- _includes/components/java/ -->

<!-- INCLUDE -->
<!-- components/java/jdk-windows.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/java#jdk-windows" %}


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

{: .note-title .text-epsilon } 
> {{ title }}
>
> {: .note-title .text-epsilon } 
>> 🔘 Temurin
>>
>> [https://adoptium.net](https://adoptium.net){:target="\_blank"}
>>
>> ```shell
>> choco install temurin17
>> ```
>>
>> <hr>{: .zone-hr }
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ JDK Location
>>> 
>>> `C:\Program Files\Eclipse Adoptium\jdk-17.X.X.X-hotspot`
>
> {: .note-title .text-epsilon }
>> 🔘 Oracle
>>
>> [https://openjdk.org](https://openjdk.org){:target="\_blank"}
>>
>> ```shell
>> choco install openjdk17
>> ```
>>
>> <hr>{: .zone-hr }
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ JDK Location
>>> 
>>> `C:\Program Files\OpenJDK\jdk-17.X.X`
