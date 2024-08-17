<!-- LOCATION -->
<!-- _includes/components/java/ -->

<!-- INCLUDE -->
<!-- components/java/jdk-macos.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/java#macos-jdk" %}


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
>> 🔘 [Eclipse Temurin](https://adoptium.net){:target="\_blank"}
>>
>> ```shell
>> brew install --cask temurin21
>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 [Amazon Corretto](https://aws.amazon.com/corretto){:target="\_blank"}
>>
>> ```shell
>> brew install --cask corretto21
>> ```
