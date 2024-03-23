<!-- LOCATION -->
<!-- _includes/components/xcode/ -->

<!-- INCLUDE -->
<!-- components/xcode/sdk.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/xcode#sdk" %}
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
> 1. Open `Xcode`
> 2. Select the platforms > `Download & Install` ![](../assets/xcode/sdk_01.png)
> 3. Enter password to acquire admin privileges > `OK` ![](../assets/xcode/sdk_02.png)
