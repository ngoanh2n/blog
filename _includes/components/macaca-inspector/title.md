<!-- _includes/docs/env/macaca-inspector/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/macaca-inspector/title.md -->
<!-- 2. include docs/env/macaca-inspector/title.md heading="###" -->

{% assign stm = "Macaca Inspector" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
