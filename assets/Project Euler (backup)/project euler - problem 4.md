---
title: 'Project Euler in R: Problem 4'
date: 'Dec. 13, 2012'
description:
categories: 'void'
---
<div class="problem">A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 * 99. 
<br /><br />
Find the largest palindrome made from the product of two 3-digit numbers.</div>

<br />
I thought this was an interesting problem because it forces us to think about numbers in terms of their digits rather than just the quantity that they represent. The easiest way to solve this problem is to convert the numbers into strings using Hadley's <em>stringr</em> package, which is, of course, not the most efficient method but it does get the job done. 

There are two functions involved in my solution. The first flips the number by converting to a string, then listing the string backwards. The second tests to see whether a number is a palindrome using the flip function. 

Finally, the solution is found by running a 2 for-loops that compute the product, check if it's a palindrome, and store the product if it's the largest so far. The solution is then just the last number assigned to <em>max</em>.

<h3>solution in code</h3>
<script src="https://gist.github.com/4288621.js"></script>

Answer: <strong>906,609</strong>