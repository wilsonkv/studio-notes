In this article we’ll look at the good, the bad, and the ugly when it comes to commenting your code.
For starters, there are really two different types of code comments. I call them documentation comments and clarification comments.

**Documentation Comments** 
Documentation comments are intended for anyone who is likely to consume your source code, but not likely to read through it. If you are building a library or framework that other developers will use, you need some form of API documentation.
The further removed from the source code your API documentation is, the more likely it is to become outdated or inaccurate over time. A good strategy to mitigate this is to embed the documentation directly into the code and then use a tool to extract it.
Here’s an example of a documentation comment from a popular JavaScript library called Lodash.

![](https://www.impactbnd.com/hs-fs/hub/145335/file-1714261536-jpg)

If you compare these comments to their online documentation, you’ll see it’s an exact match.
If you write documentation comments you should ensure that they follow a consistent standard and that they are easily distinguishable from any inline clarification comments you may also want to add. Some popular and well supported standards and tools include JSDoc for JavaScript, DocFx for dotNet, and JavaDoc for Java.
The downside of these kinds of comments is that they can make your code very “noisy” and harder to read for anyone who is actively involved in maintaining it. The good news is that most code editors support “code folding” which allows us to collapse the comments so we can focus on the code.
