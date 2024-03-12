<!-- _includes/docs/env/chocolatey/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/chocolatey/title.md -->
<!-- 2. include docs/env/chocolatey/title.md useMDHead="###" -->

{% assign stm = "Chocolatey" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
