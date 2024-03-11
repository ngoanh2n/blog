<!-- _includes/docs/env/macaca-inspector/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/macaca-inspector/title.md -->
<!-- 2. include docs/env/macaca-inspector/title.md isHeading=true -->

{% assign stm = "Macaca Inspector" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
{: .no_toc }
<hr>{: .head-hr }
