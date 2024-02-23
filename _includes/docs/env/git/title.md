<!-- _includes/docs/env/git/ -->

{% assign stm = "Git" %}
{% assign heading = include.heading %}

{% if heading %}
<{{heading}}>{{stm}}</{{heading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
