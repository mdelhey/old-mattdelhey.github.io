---
title: 'Exploring Rice University Recreation Center Data'
date: 'Feb. 14, 2013'
description: 'Rice University Recreation (Rec) center data analysis and exploration'
categories: 'blog'
type: 'draft'
---
<h3>Introduction</h3>
Here's an example of extracting interesting information from a real data set generated from our on-campus Recreation Center here at Rice University. A little background: The Rec Center is essentially our on-campus gym, open to both students (free) and community members (very not-free). To enter the Rec Center, a user must "swipe" in using their student ID or something similar. 
The data set given to me contains information regarding all swipes into the Rec center in September, 2011, including time (rounded to the nearest fifteen minutes), sex, and status (e.g. graduate student, alumni, etc.). In total, the data counted 38,374 swipes, or about 1300 entries a day. Unfortunately, I'm not able to publically release the data set but I have included all relavent R code at the bottom of this post. 
<br /><br />
<h3>Exploration: Basic Distributions</h3>
Exploring the general relationships between important variables is one way of getting a general feel of what's going on with the data. It goes without saying that we want an understanding of these basic distributions in the variables before asking any specific questions of the data. Here, I focus on the change in the number of swipes over time and the relationship between sex and status and the number of swipes.
<br />
<ul>
<li>
<h4>Entries over <u>days of the month</u></h4>
<center><img src="{{urls.media}}/rec-month.png" width=500 height=350></center>
The change in swipes over days of the month shows us that the Rec Center received about the same amount of usage over each week in September, with weekly usage decreasing slightly as the month progressed. Interestingly enough, there is a relative spike in Rec Center usage the day after Labor Day.
</li>
<li>
<h4>Entries over <u>days of the week</u></h4>
<center><img src="{{urls.media}}/rec-week.png" width=500 height=350></center>
The change in swipes over the days of the week shows us that the Rec Center saw most of its usage during the work-week, peeking on Thursday.
</li>
<li>
<h4>Entries by <u>gender</u></h4>
As we might expect, there is a discrepancy between the entrency frequency of males and females. While men use the Rec Center noticeably more women, the difference is not as significant as one might think, as males only swiped in about 15% more than females in the month of September. Women also seem to go to the Rec Center on the same days of the week as men, fitting in with the male distribution for every day except Friday and Monday, for which women are relatively more likely to swipe on Friday and men more likely on Monday.
</li>
<li>
<h4>Entries by <u>status</u></h4>
<center>
<table width=400>
<tr>
<td>Status</td><td>Count</td><td>% Composition</td>
</tr>
<tr>
<td>Undergraduate</td><td>22806</td><td>59%</td>
</tr>
<td>Graduate</td><td>6881</td><td>18%</td>
</tr>
<tr>
<td>Staff</td><td>3745</td><td>10%</td>
</tr>
<td>Faculty</td><td>1380</td><td>4%</td>
</tr>
<td>Visiting Student</td><td>338</td><td><1%</td>
</tr>
<tr>
<td>Community</td><td>231</td><td><1%</td>
</tr>
<td>Alumni</td><td>161</td><td><1%</td>
</tr>
<td>NA</td><td>2832</td><td>7%</td>
</table>
</center>
From the table we can notice that the majority of users of the Rec Center are students, making up 77% of the number of swipes. If we include staff and faculty, we are over 90% of the number of swipes. The remaining swipes are mostly those of unknown origin, most likely caused by a manual "swipe" in the Rec Center in situations where someone forgot their ID, etc. This makes it fair, I beleive, to speculate that the majority of these unknown swipes fall in student/staff/faculty. This leads us to the unsuprising conclusion that the Rec Center primarily serves the Rice population and is not signficantly utilized by non-affilates. 
</ul>

<h3>Concerns with the data</h3>
Anyone who has visited the Rec Center will now recognize a potential issue with the our data: All swipes are not created equal! In other words, swipes recorded do not necessairly reflect actual entrance and usage of the Rec Center. It is often the case that people swiping into the Rec Center are not properly recorded in one way or another. Additionally, we have no information on how long each user stays in the Rec Center or what they do while they are there. <em>We need to be careful about drawing conclusions about usage from information about swipes!</em>

<h3>Questions and Insights</h3>
With this limitation in mind, 
