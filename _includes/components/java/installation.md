<!-- _includes/docs/env/java/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/java/location.md  -->
<!-- 2. include docs/env/java/location.md platform="macos" -->
<!-- 3. include docs/env/java/location.md platform="windows" -->

{% assign platform = include.platform %}

{% assign stm_macos =  "`/usr/local/lib/node_modules/allure-commandline/`" %}
{% assign stm_windows =  "`TODO`" %}

<!-- macOS & Windows -->
{% if platform %}
    {% if platform == "macos" %}
        {% assign stm =  stm_macos %}
    {% else %}
        {% assign stm =  stm_windows %}
    {% endif %}

<!-- ALL -->
{% else %}

{% endif %}
