<!-- _includes/docs/env/java/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/java/title.md -->
<!-- 2. include docs/env/java/title.md useMDHead="###" -->

{% assign stm = "Appium" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
