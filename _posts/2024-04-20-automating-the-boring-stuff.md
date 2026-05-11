---
layout: post
title: "Automating the Boring Stuff: Chrome Extensions for Gig Work"
date: 2024-04-20 14:30:00 -0600
categories: [Automation, Development]
---

One of my favorite types of projects is identifying a highly repetitive, mundane task and engineering it out of existence.

Recently, I was looking at how gig workers interact with scheduling platforms. The process often involves refreshing pages manually, clicking through multiple modal windows, and racing against other users to claim shifts. It’s inefficient and frustrating.

### Enter the Chrome Extension

By injecting custom JavaScript into these platforms, I was able to build an automation tool that:

* Intercepts XHR requests to read schedule data before the DOM even renders it.
* Automatically evaluates shifts based on predefined user criteria (pay rate, distance, time).
* Executes the claim request instantly via background scripts.

```javascript
// A simplified conceptual example of intercepting fetch
const originalFetch = window.fetch;
window.fetch = async (...args) => {
    const response = await originalFetch(...args);

    // If this is the schedule endpoint, clone the response and parse it
    if (args[0].includes('/api/v1/shifts')) {
        response.clone().json().then(data => {
            analyzeAndClaim(data);
        });
    }
    return response;
};
```

This kind of project perfectly illustrates why I love coding: it takes a real-world frustration and solves it with logic and architecture.
