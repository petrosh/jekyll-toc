---
# See https://github.com/allejo/jekyll-toc/issues/3
---

{% capture text %}
<h2 id="foo">foo</h2>

<h2 id="bar">bar</h2>

<div class="bd-example">
    <p>foo</p>
    <h4 id="sample-heading">Sample Heading</h4>  <!-- we don't need this -->
    
    <div class="row">
        <div class="col-md-6">
            <h5 id="nested-heading">Nested Heading</h5>
        </div>
        <div class="col-md-6">
            <h4 id="heading-would-be-tracked-again">Heading would be tracked again</h4>
            <p>lorem ipsum</p>
        </div>
    </div>
</div>

<h2 id="bar2">bar2</h2>

<h3 id="bar3">bar3</h3>
{% endcapture %}

{% include toc-experimental.html html=text ignore="bd-example" %}

<!-- /// -->

<ul>
    <li><a href="#foo">foo</a></li>
    <li><a href="#bar">bar</a></li>
    <li>
        <a href="#bar2">bar2</a>
        <ul>
            <li><a href="#bar3">bar3</a></li>
        </ul>
    </li>
</ul>
