<!-- LOCATION -->
<!-- _includes/components/java/ -->

<!-- INCLUDE -->
<!-- components/java/home-windows.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference        = "/env/java#java-home-windows" %}
{% assign location_temurin = "C:\Program Files\Eclipse Adoptium\jdk-17.X.X.X-hotspot" %}
{% assign location_oracle  = "C:\Program Files\OpenJDK\jdk-17.X.X" %}


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
> ```shell
> setx /m JAVA_HOME "{JDK_LOCATION}" & refreshenv
> setx /m PATH "%PATH%;%JAVA_HOME%\bin" & refreshenv
> ```
>
> {: .warning }
> ☑️ Open `Command Prompt` with administrator privileges<br>
> ☑️ Replace `{JDK_LOCATION}` by your installation directory
>
> <hr>{: .zone-hr }
>
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> echo %JAVA_HOME%
>> java --version
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ JDK Location
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 Temurin
>>>
>>> `{{ location_temurin }}`
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 Oracle
>>>
>>> `{{ location_oracle }}`