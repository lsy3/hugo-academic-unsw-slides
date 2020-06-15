---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Sample Hugo Academic UNSW Slides"
summary: ""
authors: []
tags: []
categories: []
date: 2020-06-08T11:44:57+10:00
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: white
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
  # Choose to display slide number. true/false (default).
  slide_number: true
  # Vertical centering of slides. true (default) / false
  vert_center: true
---

<link rel="stylesheet" href="unsw-theme/reveal_custom.css">
<div class="footer">
	<p>Copyright ©2020 All Rights Reserved</p>
</div>

{{< slide background-color="#FFFFFF" class="vert-align-center" >}}

<div class="multi-column" style="position: relative; top: 10%; bottom: 0px;">
<div class="col1">
	<img src="unsw-theme/unsw-portrait.png" alt="UNSW" width="150px" style="position: relative; top: 0%; background-color: #ffe600; padding: 20px;">
</div>

<div class="col3" style="padding: 0px 20px;">

# Template Hugo Academic Slides for the University of New South Wales
Written by Luke Wicent Sy

</div>

</div>

---

## Slide 2

### h3
#### h4
##### h5
###### h6

Normal text

* list 1
* list 2

1. numbered list 1
1. numbered list 2

---

## Slide 3

<div class="multi-column">

<div class="col1">

$1/6$

</div>

<div class="col2">

$2/6$

</div>

<!-- supported up to col6 -->
<div class="col3">

$3/6$

</div>

</div>

{{% speaker_note %}}

Some personal notes!

{{% /speaker_note %}}

---

## Slide 4 - Images

<img src="unsw-theme/unsw-portrait.png" alt="Sample Image 1" height="200px">
<img src="unsw-theme/unsw-landscape.png" alt="Sample Image 2" width="300px">

---

## Slide 5 - Fragments

<p class="fragment"> hello 1 </p>
<p class="fragment"> hello 2 </p>
<p class="fragment"> hello 3 </p>
