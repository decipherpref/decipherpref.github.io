---
layout: code_page
permalink: /prompts/
title: Prompts
description:
nav: true
nav_order: 3
---

## Prompt Templates

<div class="button-container">
    <button onclick="changeEntry(-1)">Previous</button>
    <button onclick="changeEntry(1)">Next</button>
</div>

<div class="entry-container">
    <div id="entry">
    <h5 id="name"></h5>
    <p id="detail"></p>
    <h6 id="role_1"></h6>
    <pre> <code id="content_1"></code></pre>
    <h6 id="role_2"></h6>
    <pre> <code id="content_2"></code></pre>
    </div>
</div>

<script>
  var entries = {{ site.data.prompt | jsonify }};
  var currentEntry = 0;

  function displayEntry() {
    document.getElementById('name').textContent = entries[currentEntry].name;
    document.getElementById('detail').textContent = entries[currentEntry].detail;
    document.getElementById('role_1').textContent = entries[currentEntry].role_1;
    document.getElementById('content_1').textContent = entries[currentEntry].content_1;
    document.getElementById('role_2').textContent = entries[currentEntry].role_2;
    document.getElementById('content_2').textContent = entries[currentEntry].content_2;


  }

  function changeEntry(direction) {
    currentEntry += direction;
    if (currentEntry >= entries.length) currentEntry = 0;
    if (currentEntry < 0) currentEntry = entries.length - 1;
    displayEntry();
  }

  // Initial display
  displayEntry();
</script>
