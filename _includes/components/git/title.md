<!-- _includes/docs/env/git/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/git/title.md -->
<!-- 2. include docs/env/git/title.md heading="###" -->

{% assign stm = "Git" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
