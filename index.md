---
layout: custom
---


## Welcome to Toke's website which is static

Here is some text

![Toke Jensen][profile]

### Here is some smaller text

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

```markdown
This is some syntax highlighted code
```

[profile]: https://tokeloke.github.io/imgs/profile.png
