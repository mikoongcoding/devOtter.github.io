---
layout  : wikiindex
title   : wiki
toc     : true
public  : true
comment : false
regenerate : true
---

## wiki items
* [[writing-doc-test]]
* [[timeline]]
* [[nvim-shortcuts]] 
* [[iOS]]
	* [[SwiftUI-Previews]]
	* [[sRGB-내가-원하는-색을-구현하는-법]]
	* [[Picker]]
	* [[Section]]
	* [[Codable]]
* [[SwiftUI-diary]]
* [[this-blog-setting]]

---

## blog posts
<div>
    <ul>
{% for post in site.posts %}
    {% if post.public != false %}
        <li>
            <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                {{ post.title }}
            </a>
        </li>
    {% endif %}
{% endfor %}
    </ul>
</div>

