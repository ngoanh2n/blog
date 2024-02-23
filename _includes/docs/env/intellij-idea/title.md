<!-- _includes/docs/env/intellij-idea/ -->

{% assign stm = "IntelliJ IDEA Community Edition" %}
{% assign heading = include.heading %}

{% if heading %}
<{{heading}}>{{stm}}</{{heading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
