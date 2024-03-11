<!-- _includes/docs/env/nodejs/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/nodejs/title.md -->
<!-- 2. include docs/env/nodejs/title.md isHeading=true -->

{% assign stm = "NodeJS & NPM" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
