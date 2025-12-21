---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Miriam Tocino
---

## Me in 10 seconds

I’ve spent my life moving between disciplines (architecture, software, education, and operations) learning how people make sense of complexity together.

I work at the intersection of technology and human systems, helping teams find clarity, alignment, and a steady way forward.

I live in Spain. I work quietly, alongside people building meaningful things.

## Me in 10 minutes?

See [my about page](/about).

## What am I doing now?

See [my now page](/now).

## Contact me

I’m easy to reach.

If you’d like to say hello, [you can email me](mailto:miriam.tocino@gmail.com). I read everything and reply when I can.

## Search this site

Go to the [search page](/search) to search for any word or phrase.

## Books

Some ideas take more space.

I’m writing a collection of books called [Zerus & Ona](https://www.zerusxona.com), about technology, values, and growing up in a digital world.

See the books at [zerusxona.com/books](https://www.zerusxona.com/books).

## Newest articles ([see all](/blog/))

<ul style="list-style: none; padding-left: 0;">
  {% for post in site.posts limit:6 %}
    <li style="margin-bottom: 0.6em;">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## Reading

Some books I’m currently reading or returning to.

[See what I’m reading.](/reading)