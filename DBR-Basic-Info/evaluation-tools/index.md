---
layout: evaluation-tools
id: evaluation_tools_main
---

evaluation tools overview.  

{% for my_page in site.page %}
    {% if my_page.id == 'evaluation_tools_batchTestSuite' %}
            {{my_page.content}}
    {%endif%}
{%endfor%} 

{% for my_page in site.page %}
    {% if my_page.id == 'evaluation_tools_interactiveTest' %}
            {{my_page.content}}
    {%endif%}
{%endfor%} 
