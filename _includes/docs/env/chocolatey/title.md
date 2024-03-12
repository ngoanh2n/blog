<!-- _includes/docs/env/chocolatey/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/chocolatey/title.md -->
<!-- 2. include docs/env/chocolatey/title.md isHeading=true -->

{% assign stm = "Chocolatey" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
