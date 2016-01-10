---
layout: post
title: A new Chrome extension, GitHub Report Card
quote: a simple productivity tool
image: false
video: false
---

At work, we use GitHub issues for kanban style development. It's very convenient to track bugs and feature progress from the same place we get our code, but tracking progress long term is a little harder. Some pretty advanced project management tools already exist that can tie in with GitHub issues, such as [Waffle.io](https://waffle.io/).

For our small team, these kinds of tools are overkill. So I created a small Chrome extension that solves our most basic problem with GitHub issues, which is keeping track of weekly progress. My extension, the GitHub Report Card, creates a bookmark for issues closed for a one week, two week, or month long period so our project manager can keep track of our overall productivity.

With the GitHub UI, anyone can track closed issues for a given time period with a very specific search query: "is:issue closed:<2016-01-10 closed:>2016-01-17", for example. It became annoying to have to remember the dates for all this, so I used JavaScript's date tools to create the correct query for me and bookmark it.

Get the [GitHub Report Card](https://chrome.google.com/webstore/detail/github-report-card/ekilihfbhknpfdackiolkhapdolbbpae) on the Chrome extension store
