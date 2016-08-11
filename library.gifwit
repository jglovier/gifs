---
---

{
  "version":1,
  "images": [
  {% assign delimiter = ' ' %}
  {% for image in site.data.static_files %}
    {% assign path = image.path | uri_escape %}
    {
      "url": "{{ site.github.url | append: "/" | append: path | json }}",
      "keywords": "{{ image.tags | join: ' ' | json }}"
    }{% unless forloop.last %},{% endunless %}
  {% endfor %}
  ]
}
