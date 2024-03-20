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
>> 🔘 [Temurin](https://adoptium.net){:target="\_blank"}
>>
>> {: .note-title .text-epsilon } 
>>> ✅ Install Cask
>>>
>>> ```shell
>>> brew tap homebrew/cask-versions
>>> ```
>>
>> {: .note-title .text-epsilon } 
>>> ✅ Install Specific Verion
>>>
>>> ```shell
>>> brew install --cask temurin17
>>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 [Oracle](https://openjdk.org){:target="\_blank"}
>>
>> {: .note-title .text-epsilon } 
>>> ✅ Install Specific Verion
>>>
>>> ```shell
>>> brew install openjdk@17
>>> ```
>>
>> {: .note-title .text-epsilon } 
>>> ✅ Symlink For Finding JDK
>>>
>>> ```shell
>>> sudo ln -sfn /usr/local/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk
>>> ```
