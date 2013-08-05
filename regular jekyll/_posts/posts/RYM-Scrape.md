---
title: 'Using Python for Web-Scraping: RateYourMusic.com'
date: 'Mar. 11, 2013'
description: 'A quick case study on using Python for web scraping, using the awesome rateyourmusic.com as an example.'
categories: 'blog'
type: 'draft'
---
While tons of awesome data sets are available on the web in easy-to-grab formats, sometimes getting the data we want involves a little bit more work. One special case of this effect are web-databases: sites that are designed to be accessed by web users and don't provide flat data sets yet store tons of interesting information. 

In this post I want to talk about scraping one of my favorite web-databases, <a href="http://www.rateyourmusic.com"RateYourMusic.com</a>. This site allows users to -- not supprisingly -- rate music, among a bunch of other cool features. One of the best features on the site is Charts, which arregrates the highest rated albums on the site using an alogirthim that looks at average rating, number of ratings, etc. What if we wanted to do an exploratory  analysis of these highest-rated albums on the site? There are no flat files in sight, but the data is neatly organized. In this sense, the website <em>is</em> the API. I think this is a perfect situation for web-scraping.


