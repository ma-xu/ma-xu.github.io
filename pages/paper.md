---
layout: page
title: Paper
description: my papers
keywords: Xu Ma, 马旭
comments: true
menu: Paper
permalink: /paper/
---



<p class="repo-list-description">
	If any of the following papers can help your learning, I hope you can cite it, thanks.
</p>

--  Xu Ma



## My papers


<ol class="repo-list">
	{% for paper in site.data.papers %}
    	<li class="repo-list-item">
	        <h3 class="repo-list-name">
	          <a >{{ paper.name }}</a>
	        </h3>
	        <p class="repo-list-description">
	            {{ paper.reference }}
	        </p>
	    </li>
    {% endfor %}
</ol>

