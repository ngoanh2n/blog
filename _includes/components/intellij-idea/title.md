<!-- _includes/docs/env/intellij-idea/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/intellij-idea/title.md -->
<!-- 2. include docs/env/intellij-idea/title.md heading="###" -->

{% assign stm = "IntelliJ IDEA Community Edition" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
