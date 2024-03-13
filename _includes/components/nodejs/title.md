<!-- _includes/docs/env/nodejs/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/nodejs/title.md -->
<!-- 2. include docs/env/nodejs/title.md heading="###" -->

{% assign stm = "NodeJS" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
