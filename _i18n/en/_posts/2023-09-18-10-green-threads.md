---
layout: post
title:  "Exploring Green Threads for .NET Runtime!"
tagline: New results
date: 2023-09-18 09:32
categories: [Blog]
tags: [CodeGlass, Development, CodeGlass Development]
post_image: /assets/img/blog/GreenThreads.jfif
---

🔍 Exploring Green Threads for .NET Runtime

Recently, I've been closely following the green thread experiment in the .NET Runtime Lab. The goal was to understand the costs and benefits of introducing green threads to the .NET Runtime environment. Green threads promised to simplify the programming model, making it easier to write synchronous code without compromising on scalability and performance.

🚀 I was hopeful that CodeGlass could benefit from this and Improve it's throughput of 8 million ELT Calls. However, the results were not as anticipated.

📊 In the prototype, the performance of green threads was competitive with the current async/await model. But it wasn't as fast or faster than async. There were also challenges like the complex interaction between green threads and the existing async model, and issues with native code interop in the green threads model.

🛑 As a result, the decision was made to place the green thread experiment on hold. The focus will remain on improving the existing async/await model for developing asynchronous code in .NET.

While the results weren't what I had hoped for, it might cause Microsoft to focus more on improving its current async/await model, which would also benefit me greatly.

And it's always enlightening to see such experiments in the tech world. It helps us understand the potential and limitations of new approaches.

To read more: [https://github.com/dotnet/runtimelab/issues/2398](https://github.com/dotnet/runtimelab/issues/2398)