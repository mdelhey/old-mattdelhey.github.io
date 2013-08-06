---
title: 'Project Euler in R: Problem 1 (and Python!)'
date: 'Nov. 04, 2012'
description:
categories: 'void'
---
<h3>Introduction</h3>
In case you didn't already know, <a href="http://projecteuler.net/" target="_blank">Project Euler</a> is a website that poses computational mathematicsquestions for users to complete using a programming language of their choice. While it may seem dry at first, the problems are suprisingly addicting and kick-up in difficulty rather quickly. 


<br />
<br />



Since first using the website I have set a lofty goal: to complete all of the Project Euler problems using only the R programming language. The motivation for this is two-fold: to improve my computation and mathematical problem solving skills while also increasing my knowledge of R-- while of course having fun in the process! At the time of this writing there are currently over 400 problems, so grab a beverage of choice, put on your mathematical thinking caps and join me for the ride!

<br /><br />

<h3>Moving on to the problem...</h3>

<div class="problem">If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
<br /><br />
Find the sum of all the multiples of 3 or 5 below 1000.</div>
<br />
Not surprisingly, the first problem is an easy one to get us started. My approach to the problem was to implement a sequential, brute-force algorithm: take all the values below 1000, store a new vector of multiples by checking if each individual value is divisible by 3 and 5 via the modulo operator, and finally taking the sum of these multiples. Not efficient, but easy to read and fast to implement. The code this approach can be found below. 

<script src="https://gist.github.com/4191776.js"></script>

<h3>Bonus: the solution in python!</h3>
I also solved this problem in python using more traditional <code>for</code> and <code>if</code> statements.

<script src="https://gist.github.com/4298800.js"></script>

Answer: <strong>233,168</strong>