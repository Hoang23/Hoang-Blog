---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Graphs"
subtitle: ""
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
Graphs are am anstractopm pf relational data

Trees are connected graphs without cycles

Simple graphs
- undirected
- dont have self loops
- at most have 1 pair of edges between 2 vertices

Cycles
- a sequence of steps cycling the start and end of a vertex?

Adjacency matrices can be used to represent graphs in Python

Prim's algorithm finds spanning tree by iteratively adding extension edge to already connected subgraph

