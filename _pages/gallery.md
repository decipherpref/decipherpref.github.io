---
layout: page
permalink: /gallery/
title: Gallery
description:
nav: true
nav_order: 4
---

## Pair-wise Preferences Comparison
Data instances from Reddit:TLDR dataset. Human preference factors are shown under each summaries. **Same factors** between summaries will be marked using the **same color**. Human preferred summary will have **(Preferred)** label in title.

<div id="content">
    {% for item in site.data.comparisons %}
    <div class="entry">
      <button class="toggle-content">Show/Hide Post Content</button>
        <div class="content-container" style="display: none;">
          <h4>{{ item.title }}</h4>
         <p>{{ item.content }}</p>
      </div>
    <div class="passage_container">
        <div class="passage">
            <h4>{{ item.passage1.title }}</h4>
            <p>{{ item.passage1.content }}</p>
        </div>
        <div class="passage">
            <h4>{{ item.passage2.title }}</h4>
            <p>{{ item.passage2.content }}</p>
        </div>
    </div>
    <div class="passage_container">
        <div class="label_content">
              {% for label_word in item.passage1.label %}
                  <span class="label-box" data-label="{{ label_word }}">{{ label_word }}</span>
              {% endfor %}
        </div>
        <div class="label_content">
              {% for label_word in item.passage2.label %}
                  <span class="label-box" data-label="{{ label_word }}">{{ label_word }}</span>
              {% endfor %}
        </div>
    </div>
    </div>
    {% endfor %}
</div>


<div class="button-container">
  <button onclick="changeEntry(-1)">Previous</button>
  <button onclick="changeEntry(1)">Next</button>
</div>

<script>
var currentEntry = 0;
var entries = document.querySelectorAll('.entry');

function changeEntry(direction) {
    entries[currentEntry].style.display = 'none';
    currentEntry += direction;
    currentEntry = (currentEntry + entries.length) % entries.length;
    entries[currentEntry].style.display = 'block';
}

// Initialize with the first entry
changeEntry(0);

var colors = ['#55efc4', '#81ecec', '#74b9ff', '#a29bfe', '#dfe6e9',
              '#00b894', '#00cec9','#0984e3','#6c5ce7', '#b2bec3',
              '#C0392B', '#F5B7B1', '#C39BD3', '#D2B4DE', '#A9CCE3', '#2E86C1', 
              '#A3E4D7', '#73C6B6', '#82E0AA', '#F5CBA7', '#F5B041',
              '#DAF7A6', "#FFC300", "#d63031", '#fdcb6e', '#e84393']; 

document.addEventListener('DOMContentLoaded', function() {
    var labelElements = document.querySelectorAll('.label-box');
    var labelColors = {};
    var colorIndex = 0;

    labelElements.forEach(function(label) {
        var labelText = label.getAttribute('data-label');
        if (!labelColors[labelText]) {
            labelColors[labelText] = colors[colorIndex % colors.length];
            colorIndex++;
        }
        label.style.backgroundColor = labelColors[labelText];
    });
});

document.addEventListener('DOMContentLoaded', function() {
    // Event listener for all toggle buttons
    document.querySelectorAll('.toggle-content').forEach(function(button) {
        button.addEventListener('click', function() {
            // Find the next sibling element and toggle its visibility
            var content = this.nextElementSibling;
            content.style.display = content.style.display === 'none' ? 'block' : 'none';
        });
    });
});

</script>