---
title: SMC
layout: page
blog_index: true
permalink: smc/
smc:
    - 9/18 Wednesday - Day 1
    - 9/19 Thursday - Day 2
    - 9/20 Friday - Day 3
    - 9/21 Saturday - Day 4
    - 9/22 Sunday - Day 5
    - 9/23 Monday - Day 6
    - 9/24 Tuesday - Day 7
    - 9/25 Wednesday - Day 8
    - 9/26 Thursday - Day 9
    - 9/27 Friday - Day 10
    - 9/28 Saturday - Day 11
    - 9/29 Sunday - Day 12
    - October
    - 10/1 Tuesday - Day 13
    - 10/2 Wednesday - Day 14
    - 10/3 Thursday - Day 15
    - 10/4 Friday - Day 16
    - 10/5 Saturday - Day 17
    - 10/6 Sunday - Day 18
    - 10/7 Monday - Day 19
    - 10/8 Tuesday - Day 20
    - 10/9 Wednesday - Day 21
    - 10/10 Thursday - Day 22
    - 10/11 Friday - Day 23
    - 10/12 Saturday - Day 24
    - 10/13 Sunday - Day 25
    - 10/14 Monday - Day 26
    - 10/15 Tuesday - Day 27
    - 10/16 Wednesday - Day 28
    - 10/17 Thursday - Day 29
    - 10/18 Friday - Day 30
---
<ul>
    {% for list in page.smc %}
    <li class="post-item">
        <a class="post-title" href="{{ list }}"><span>{{ list }}</span></a>
    </li>
    {% endfor %}
</ul>

# Term 1 - Compulsory Subjects
- **Music Perception & Cognition** (5 ECTS)
- **Machine Learning for Sound and Music** (5 ECTS)  
- **Digital Signal Processing for Sound and Music** (5 ECTS)
- **Research Methodology** (5 ECTS)

# Term 2 - Compulsory Subjects
- **Music Information Retrieval** (5 ECTS)
- **Symbolic Music Analysis and Computational Musicology** (5 ECTS)
- **Generative Algorithms for Sound and Music** (5 ECTS)

# Term 3 - Optional Subjects
- **Sound Communication** (5 ECTS)

# Second Year Considerations
- **Machine Learning** (5 ECTS)
- **Practicum** (20 ECTS)
- **Advanced Computing Techniques for Sound and Music** (5 ECTS)

# Writings
<ul>
    {% for post in site.posts %}
    {% unless post.draft == true or post.series %}
    <li class="post-item">
        <a class="post-title" href="{{ post.url }}"><span>{{ post.title }}</span></a>
        <div class="post-date"><i>{{ post.date | date: '%B %-d, %Y' }}</i></div>
    </li>
    {% endunless %}
    {% endfor %}
</ul>
