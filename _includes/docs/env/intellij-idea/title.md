<!-- _includes/docs/env/intellij-idea/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/intellij-idea/title.md -->
<!-- 2. include docs/env/intellij-idea/title.md isHeading=true -->

{% assign stm = "IntelliJ IDEA Community Edition" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
