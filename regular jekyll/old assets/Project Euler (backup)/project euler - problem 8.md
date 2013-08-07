---
title: 'Project Euler in R: Problem 8'
date: 'Mar. 04, 2013'
description:
categories: 'void'
---
<div class="problem">Find the greatest product of five consecutive digits in the 1000-digit number:
<br /><p class="center_copy">[massive number]</p></div>
<br />
I found this problem to be a lot of fun. Although it makes me wish there was a better way for dealing with digits than converting to strings, albeit working with strings is easy using Hadley's <em>stringr</em> package.
<br /><br />
I tackled this problem in four major steps:
<ol>
<li>Load the number in as a string</li>
<li>Convert the string to individual digits</li>
<li>Find all groups of 5 consecutive digits</li>
<li>Find the largest product out of all of our groups</li>
</ol>
While my solution certainly isn't elegant (I convert strings in every step!), it certainly works and follows my first intuition in solving the problem.

<script src="https://gist.github.com/mattdelhey/5080772.js"></script>

Answer: <strong>40,824</strong>
