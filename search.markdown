---
layout: default
title: Search
permalink: /search/
---

## Search

<input
  type="search"
  id="search-input"
  placeholder="Search…"
  style="width: 100%; padding: 10px; font-size: 1em;"
/>

<p id="search-count" style="margin-top: 1em;"></p>

<div id="search-results"></div>

<script>
const posts = [
  {% for post in site.posts %}
  {
    title: {{ post.title | jsonify }},
    url: {{ post.url | relative_url | jsonify }},
    content: {{ post.content | strip_html | strip_newlines | jsonify }}
  }{% unless forloop.last %},{% endunless %}
  {% endfor %}
];

const input = document.getElementById("search-input");
const results = document.getElementById("search-results");
const count = document.getElementById("search-count");

function escapeRegex(str) {
  return str.replace(/[.*+?^${}()|[\]\\]/g, "\\$&");
}

function highlight(text, query) {
  const safeQuery = escapeRegex(query);
  const regex = new RegExp(`\\b(${safeQuery})\\b`, "gi");
  return text.replace(regex, "<mark>$1</mark>");
}

function snippet(content, query) {
  const safeQuery = escapeRegex(query);
  const regex = new RegExp(`\\b${safeQuery}\\b`, "i");
  const match = content.match(regex);
  if (!match) return "";

  const index = match.index;
  const start = Math.max(0, index - 80);
  const end = Math.min(content.length, index + 80);
  return "…" + content.slice(start, end) + "…";
}

input.addEventListener("input", function () {
  const query = this.value.trim();
  results.innerHTML = "";
  count.textContent = "";

  if (query.length < 2) return;

  const safeQuery = escapeRegex(query);
  const regex = new RegExp(`\\b${safeQuery}\\b`, "i");

  const matches = posts.filter(post =>
    regex.test(post.title) || regex.test(post.content)
  );

  count.textContent = `${matches.length} result${matches.length !== 1 ? "s" : ""} for “${query}”`;

  matches.forEach(post => {
    const div = document.createElement("div");
    div.style.marginBottom = "2em";

    const title = highlight(post.title, query);
    const excerpt = highlight(snippet(post.content, query), query);

    div.innerHTML = `
      <h3><a href="${post.url}">${title}</a></h3>
      <p>${excerpt}</p>
    `;

    results.appendChild(div);
  });
});
</script>

<style>
mark {
  background: #ffeb3b;
  padding: 0 2px;
}
</style>
