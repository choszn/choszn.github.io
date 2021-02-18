---
layout: home
---

On the prairie we follow some rules.

- **Room** is an atomic, autonomous note in Markdown.
  - Every room has a door, a descriptive link.
- **Hall** contain *doors* to related *rooms* to depict a common theme.
- **Terrace** is a .md note that draws connections from the rooms to the context of the prairie.
- **Chimney** is a .md note that is the unifying narrative of everything above.



While living on the prairie, there’s a lot to learn, starting from the [[[50-Glossary]]].



## Doors

We can use notes in Markdown to build rooms, halls, and more.

Most importantly, we want to tell meaningful stories that encompass the [elements](/2020/12/25/Elements-Of-A-Prairie-Home) of a prairie style home.
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>