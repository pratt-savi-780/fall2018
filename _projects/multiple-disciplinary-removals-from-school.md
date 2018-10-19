---
layout: project-page
title: "Multiple Disciplinary Removals from School"
linkname: multiple-disciplinary-removals-from-school
author: "Kate Sutton"
tagline: "This project analyzes the rate of students that were suspended or otherwise removed from school for disciplinary reasons multiple times in New York City public schools during the 2015-2016 school year. Suspensions, expulsions, and other forms of removing a student from school as a disciplinary measure, especially on a repeated basis, are criticized for putting students at increased risk of being incarcerated later in life. "
location:
    - place: New York, NY USA
project-link:
    - href: https://conditional-moustache-removals.glitch.me/
tags:
    - tag: school discipline
    - tag:  school to prison pipeline
    - tag:  multiple removals
    - tag:  school suspensions
thumbnail-path: img/multiple-disciplinary-removals-from-school/jMHFMMY.png
img-folder: ../../img/multiple-disciplinary-removals-from-school/
timestamp: 10/17/2018 23:14:29
---
In light of the impact that student involvement in the disciplinary system during their k-12 years can have on their likelihood of being incarcerated as adults, I looked at some of the first school discipline data released by New York City's Department of Education. I chose to focus on students with multiple removals, meaning that they were suspended or otherwise removed from school more than once, because this indicates greater contact with school disciplinary measures. 

The dataset includes the number of students at each school that were removed from school multiple times, as well as the demographic breakdowns of multiple removals based on race, disability, gender, grade level, English language learners, and students living in temporary housing. For this project I chose to analyze the overall rate of multiple removals, as well as the demographic breakdowns for race, disability, English language learners, and students living in temporary housing. The data was released in July of 2018 and is from the 2015-2016 school year. Many schools have incomplete data, are lacking data entirely, or had their data suppressed due to concerns that students could be identified. If the Department of Education continues to release this dataset for subsequent school years, it will be interesting to see if data will be available on more of New York City’s schools in the future.

Though deeper statistical tests would be required to analyze if any group is truly disproportionately suspended at any school, this analysis is an initial pass at the data to visualize the rates at which schools are suspending both their entire student body, as well as certain marginalized groups. To visualize the overall rate of multiple removals, I made a choropleth based on the percent of the student population with multiple removals. The lowest rate was 0.2 percent and the highest rate was 16.2% of the student population. For the demographic analyses, I visualized school points as red if the group in question was represented at a higher rate amongst students with multiple removals than they were in the student body as a whole. For example, if 50% of students with multiple removals had a disability, whereas only 30% of the student population had a disability, that point would be represented as red. This is of course not a perfect analysis, and this is where a stastical test would have to be performed to determine if a certain group was disproportionately suspended. But for this initial analysis I am only doing a strict comparison of the rates. 

![]({{ page.img-folder }}jMHFMMY.png)

The map offers people a dropdown to select which category of data they are interested in exploring. Looking at the overall rate of multiple removals shows a wide array of suspension rates throughout the city. If the data were determined to be robust enough, it might be interesting to compare the average suspension rates in New York City’s 33 school districts to determine if any districts struggle with this more than others. 

![]({{ page.img-folder }}7G725v7.png)

One way I like to look at this data is to look at co-located schools, or buildings where more than one school shares space. Co-located schools often have similar demographics, may serve students from similar areas, and share many aspects of their environment, such as the school building itself, but they have completely different administrations and function as separate schools. One group of co-located schools I found to be interesting was the 3 schools at 5800 Tilden Avenue in East Flatbush, Brooklyn. Their sizes vary from 350 to 600 students, they’re all high schools, and their rates of multiple removals vary from 1.2% to 10.7%. 

![]({{ page.img-folder }}acy1ET2.png)

Data on English language learners was very infrequently available, with only 15 schools. At most of these schools, the rate of English language learners in the students with multiple removals was higher than in the general population. 

![]({{ page.img-folder }}aSDcjTN.png)

Comparing rates of multiple removals based on race was more challenging since there were more categories to consider. One thing worth wondering about is why no schools tracked multiracial students in their multiple removals data. The only categories on which they reported data were Asian, Black, Hispanic, and White students. And at some schools, data was available for some races but not all. This could be due to data suppression reasons, but it makes comparisons challenging. I chose to symbolize the points as red in this analysis if any group of students of color was represented at a higher rate amongst students with multiple removals than in the general population. And indeed some schools had disproportionate suspension rates for Black students but not Hispanic students, while some schools had disproportionate suspension rates for more than one group of students of color, and some did not have disproportionate suspension rates for any group of students of color.

![]({{ page.img-folder }}vjSHotc.png)

The analysis for students with disabilities was striking in that all schools that reported data on that demographic had a higher rate of students with disabilities amongst students with multiple removals than in the overall school population. 

![]({{ page.img-folder }}Go5yMFA.png)

Few schools had data available on students in temporary housing. There is also no school-level data on homelessness rates. Instead, I used data from the New York State Department of Education on the number of homeless students in the district as a whole. This is not an ideal comparison since a school’s rate of homelessness could vary widely compared to the district average, but it provides a ballpark. 
