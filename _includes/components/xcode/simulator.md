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
{% assign reference = "/env/xcode#simulator" %}
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
> 2. Open `Platforms`<br>
> _Navigation route:_ `Xcode` > `Settings...` > `Platforms` ![](../assets/xcode/simulator_01.png)
> 3. Open simulator picker: _Add_ icon > `iOS...` ![](../assets/xcode/simulator_02.png)
> 4. Select desired simulators > `Download & Install` ![](../assets/xcode/simulator_03.png)
> 5. Open a siumlator
> ```shell
> opem -a simulator
> ```
> ![](../assets/xcode/simulator_04.png)
