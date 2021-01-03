---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Sorting algorithms"
subtitle: "this is a test"
summary: ""
authors: []
tags: ["python"]
categories: []
date: 2020-08-26T23:12:02+10:00
lastmod: 2020-08-26T23:12:02+10:00
featured: false
draft: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Sorting
Selection and Insertion sort are both kind of inefficient compared to other sorting algorithms such as merge and quick sort
There are other sorts such as heap sort and tim sort (python's lst.sort() uses tim sort)

Selection Sort - swap elements if they are smaller
[3,6,1,8,2] after first iteration = [1,6,3,8,2] then second iteration [1,2,3,8,6] ... third nothing then fourth [1,2,3,6,8] and dont need to compare last element as it will be highest value

Inseration Sort - checks if current index is lower then previous index thus shuffling it down for example 2 is shuffled down
- holds 2 lists a sorted and unsorted list
- very efficient when working with nearly sorted list
[3,6,1,8,2] after first iteration = [3,6,1,8,2] after second = [1,3,6,8,2] after third = [1,3,6,8,2] and then [1,2,3,6,8]



