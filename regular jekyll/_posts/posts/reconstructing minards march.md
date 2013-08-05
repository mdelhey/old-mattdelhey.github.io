---
title: 'Reconstructing Napoleons Failed March to Russia'
date: 'Nov. 11, 2012'
description: 'description'
categories: 'blog'
---
<img src="http://qed.princeton.edu/getfile.php?f=Minard_carte_figurative.jpg" />

Above is possibly one the most famous statistical graphics ever created, found in nearly every history text-book that discusses Napoleon's failed invasions of Russia in 1812. The graphic was originally created by <a href="http://en.wikipedia.org/wiki/Charles_Joseph_Minard">Charles Joseph Minard</a>, a statistician and engineer way ahead of his time.

The reason this graphic is so good is that it tells a story for the viewer allowing us to visualize the march. By following along the graphic, we get a real feel for just how bad Napoleon's march must have been. My favorite observation is how the number of troops about halves every time the army crosses a river-- something that must of been pretty treacherous in the freezing temperatures. 

<h3>Representing the march with ggplot2</h3>
We want to represent the above graphic using ggplot2's grammar of graphics. In order to do this, we need to determine the layers that we want to create, what data is required for each layer, and what geometries we need to represent the data like Minard. So let's break down each variable utilized in Minard's graphic and convert them to layers we can implement using ggplot2: 

<ul>
<li>Map of Russia, including names of cities. Created using the <em>map</em> package & geom_polygon and a text file containing city names with location & geom_text. 
<li>The number of troops. This is mapped to the size of the line using geom_path.</li>
<li>Direction of the army, represented by the tan/black colors and including information on the split and re-joining. Mapped using the color and lineend properties of geom_path.</li>
<li><strong>Missing:</strong> the temperature and dates of the troops as they made their way across Russia. This data could reasonably be added by superimposing geom_line and geom_point layers on the bottom of the plot.</li>
<li><strong>Also Missing:</strong> geographical information for the map of Russia, including Rivers, etc.</li>
</ul>

Luckily, the data needed for the non-missing variables is all easily obtainable. The troop and city data is provided by Hadley Wickham on his <a href="http://stat405.had.co.nz/">stat405 website</a> (from which I got this example) and the map data is available from the maps package. 

<h3>Putting it all in R</h3>
The hard part is over. Here's our graphic and how it's implemented using our grammar of graphics and ggplot2. While it doesn't look quite as good as Minard's plot, we gain a lot of power by being able to create the graphic automatically as opposed to by hand -- and it only took us a few minutes to create! 

<img src="{{urls.media}}/minard.png" />

<pre>
library(ggplot2)
library(maps)
 
troops <- read.table("minard-troops.txt", header = T)
cities <- read.table("minard-cities.txt", header = T)
russia <- map_data("world", region = "USSR")
 
ggplot(troops, aes(x = long, y = lat)) +
  geom_polygon(aes(x = long, y = lat, group = group), data = russia, fill = "white") +
  geom_path(aes(size = survivors, color = direction, group = group), lineend = "round") +
  geom_text(aes(label = city), size = 3, data = cities) +
  xlab(NULL) + ylab(NULL) + coord_equal(xlim = c(23, 38), ylim = c(50, 60)) +
  scale_colour_manual(values = c("bisque2","grey10"))
</pre>