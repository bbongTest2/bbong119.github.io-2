---
layout: evaluation-tools
id: evaluation_tools_main
---

evaluation tools overview.  

{{ page.id }}

{{ evaluation_tools_main.url }}  

{{ evaluation_tools_batchTestSuite.url }}  

Test if update
{include file="{{ site.evaluationTools_batchTestSuite }}/index.html"}

<head>
    <meta charset="utf-8" />
    <!--import引入-->
    <link rel="import" href="{{ site.evaluationTools_batchTestSuite }}index.html=" id="page1"/>
</head>

<script type="text/javascript">
    document.write(page1.import.body.innerHTML);
</script>
