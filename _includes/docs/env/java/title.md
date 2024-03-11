<!-- _includes/docs/env/java/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/java/title.md -->
<!-- 2. include docs/env/java/title.md isHeading=true -->

{% assign stm = "Java" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
{: .no_toc }
<hr>{: .head-hr }
