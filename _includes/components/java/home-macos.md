<!-- LOCATION -->
<!-- _includes/components/java/ -->

<!-- INCLUDE -->
<!-- components/java/home-macos.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/java#macos-java-home" %}
{% assign location_temurin  = "/Library/Java/JavaVirtualMachines/temurin-XX.jdk" %}
{% assign location_corretto = "/Library/Java/JavaVirtualMachines/amazon-corretto-XX.jdk" %}


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
>
> <hr>{: .zone-hr }
>
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> echo $JAVA_HOME
>> java --version
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 Eclipse Temurin
>>>
>>> `{{ location_temurin }}`
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 Amazon Corretto
>>>
>>> `{{ location_corretto }}`