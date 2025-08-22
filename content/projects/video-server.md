---
title: "Vidfy"
date: 2025-03-24
draft: false
github_link: "https://github.com/AubreyFeldker/vidfy"
author: "Aubrey Feldker"
badges:
    - "MongoDB"
    - "Scalable Servers"
    - "APIs"
    - "Electron"
    - "ffmpeg"
image: website/images/projects/vidfy.png
description: "Scalable video server built for cataloguing videos across multiple storage locations, balancing size constraints and response times."
---

Built for my Multimedia Systems class, Vidfy is a scalable video server programmed in JavaScript with an Electron client interface. The server is composed of several independent units: a master node for obtaining client requests and managing other nodes, video storage nodes that acquire and process video files, and a metadata node for processing tags and other video metadata. Nodes interact with each other and the client through asynchronous HTTP requests, minimizing server bottlenecks.

When videos are uploaded to the server, they are sent directly to a free video node, which utilizes the ffmpeg package to compress the video and create a very small preview thumbnail for future searching. Due to the load of video processing, it takes a while for each video to be uploaded. However, thanks to the atomic structure of video nodes, a stress test of mass uploading over 1000 videos at once allowed them to be eventually processed with minimal client-side disruption.

Videos can be searched forusing a combination of TF-IDF tag search and how frequently a video is searched for. This is all processed within the metadata node, whos data is passed to the appropriate video server node to send back to the client.