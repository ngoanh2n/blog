<!-- _includes/docs/env/nodejs/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/nodejs/title.md -->
<!-- 2. include docs/env/nodejs/title.md useMDHead="###" -->

{% assign stm = "NodeJS" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
