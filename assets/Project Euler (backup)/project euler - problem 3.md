---
title: 'Project Euler in R: Problem 3'
date: 'Dec. 04, 2012'
description:
categories: 'void'
---
<div class="problem">The prime factors of 13195 are 5, 7, 13 and 29.
<br />
What is the largest prime factor of the number 600851475143 ?
</div>

<br />
This rather straightforward question gave me a bit of trouble at first. The issue I had with it wasn't solving the problem per se but rather making sure my solution could be ran in a reasonable amount of time (i.e., the speed of my solution). 
<br /><br />
My general appraoch to the problem was to generalize it by creating a function that could tell me the largest prime factor of any integer. After several optimizations, I came up with the following algorithm: starting with the square root of the number we want to find the largest prime factor of, work backwards to 0 testing each number as a factor and then as a prime. 
<br /><br />
The key here is working backwards! This is the only way to compute the largest prime factor in a reasonable amount of time for large numbers.

<script src="https://gist.github.com/4211349.js"></script>

I also want to point out that I used the isprime() function from the <i>gmp</i> library in order to further increase speed. Of course, this can be easily implemented in R was a standard function. 


Answer: <strong>6,857</strong>