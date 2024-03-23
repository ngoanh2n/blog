<!-- LOCATION -->
<!-- _includes/components/xcode/ -->

<!-- INCLUDE -->
<!-- components/xcode/ide.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/xcode#ide" %}
{% assign link_download = "https://xcodereleases.com/?scope=release" %}


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
>> ℹ️ Prerequisites
>> - macOS machine with version 10.15.4 or upper
>> - Minimum space requirement for Xcode download and installation
>> - An Apple ID
>> - Membership in the Apple Developer Program (For Real Devices)
>
>
> 1. Visit [https://xcodereleases.com]({{ link_download }}){:target="\_blank"}
> 2. Open `Xcode_XX.X.xip`
> 3. Move `Xcode` to the `Applications`
