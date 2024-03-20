<!-- LOCATION -->
<!-- _includes/components/nodejs/ -->

<!-- INCLUDE -->
<!-- components/nodejs/installation-windows.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference     = "/env/nodejs#windows" %}
{% assign command       = "choco install nodejs-lts" %}
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
> {: .note-title .text-epsilon }
>> 🔘 Chocolatey
>>
>> Open `Command Prompt` (administrator privileges)
>> ```shell
>> {{ command }}
>> ```
>>
>> {: .note-title .text-epsilon }
>>> ✅ Path Setting
>>>
>>> ```shell
>>> setx /m PATH "%PATH%;C:\Program Files\nodejs" & refreshenv
>>> setx /m PATH "%PATH%;C:\{USER}\AppData\Roaming\npm" & refreshenv
>>> ```
>>>
>>> {: .warning }
>>> Replace `{USER}` by your current username!
>
> {: .note-title .text-epsilon }
>> 🔘 Setup Wizard
>>
>> 1. Visit [{{ download_link }}]({{ download_link }}){:target="\_blank"}
>> 2. Click `Windows Installer`
>> 3. Open the {{ download_file }} file in `Downloads`
>> 4. Do installation procedures of Setup Wizard
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
>> `C:\Program Files\nodejs`<br>
>> `C:\Program Files\nodejs\node_modules\npm`
>>
>> {: .note-title .text-epsilon }
>>> NPM Packages
>>>
>>> `C:\{USER}\AppData\Roaming\npm`