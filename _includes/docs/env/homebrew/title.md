<!-- _includes/docs/env/homebrew/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/homebrew/title.md -->
<!-- 2. include docs/env/homebrew/title.md isHeading=true -->

{% assign stm = "Homebrew" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
