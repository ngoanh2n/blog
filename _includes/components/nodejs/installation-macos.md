<!-- LOCATION -->
<!-- _includes/components/nodejs/ -->

<!-- INCLUDE -->
<!-- components/nodejs/installation-macos.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference     = "/env/nodejs#macos" %}
{% assign command       = "brew install node@20" %}
{% assign download_link = "https://nodejs.org/en/download" %}
{% assign download_file = "`node-v20.xx.x-xxx.msi`" %}


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
> ```shell
> {{ command }}
> ```
>
> <hr>{: .zone-hr }
> 
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> node --version
>> npm --version
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>> 
>> `/usr/local/lib/node_modules`<br>
>> `/usr/local/lib/node_modules/npm/node_modules`

