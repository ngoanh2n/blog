<!-- _includes/docs/env/git/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/git/title.md -->
<!-- 2. include docs/env/git/title.md useMDHead="###" -->

{% assign stm = "Git" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
