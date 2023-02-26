---
title: "ChatGPT and Me"
date: 2023-02-26
# weight: 1
# aliases: ["/first"]
tags: ["ChatGPT", "openai.com", "Linting", "MATLAB", "Jupyter", "Python", "JavaScript", "Optimization", "Productivity"]
author: "Travis Vilac"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "What I have been using ChatGPT for (with some easy to follow examples)"
# canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: false
ShowRssButtonInSectionTermList: false
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/traviscancode604/victus/blob/main/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

## Captain's Log
I have been keeping busy after work and on weekends lately with side projects. I'll address the main one I am working on in a future blog post, but one tool that has been helpful in keeping things moving along is [ChatGPT](https://chat.openai.com).

Here are three ways I've been using it to enhance my productivity:

## 1 - Assist with Linting Code
Linting is great. It helps ensure that your code adheres to a preferred coding standards. I am using [ESLint](https://eslint.org/) and the [AirBNB Style Guide](https://github.com/airbnb/javascript) For the JavaScript projects I am working on. Sometimes, if I revisit code I haven't looked at for a few months and didn't use a linter on (I know, shame on me), ChatGPT can provide a quick means to clean up the code without having to decipher the linting rule.

To show an example that's easy to understand, consider the following:

> **TV**: `eslint` is flagging this on `arrow-parens` rule, how do I fix this code snippet to pass the linter:
> ```js
> profileFields.skills = skills.split(',').map(skill => skill.trim());
>```

> **ChatGPT**: To pass the `eslint` `arrow-parens` rule with this code snippet, you can add parentheses around the parameter "skill" in the arrow function:
>
>```js
> profileFields.skills = skills.split(',').map((skill) => skill.trim());
>```
> This tells `eslint` that you are intentionally using an arrow function with a single parameter named "skill". By adding the parentheses, you are being more explicit about the parameter and avoiding the linter error.

Not bad.

## 2 - Another Starting Point for Problem Solving
Google, Stack Overflow and vendor documentation are still my preferred starting points for planning out an approach to solve a problem, but having another tool to help with this is quite the luxury. Asking a basic question to ChatGPT and seeing what it outputs can be useful. You don't need to (and in a lot of cases, should not) take the answer verbatim, but it can be helpful in supplementing you on your quest to solve your current problem.

To use a real world example, [this blog post](https://blogs.mathworks.com/matlab/2023/01/30/official-mathworks-matlab-kernel-for-jupyter-released/) was shared with me recently about adding the MATLAB kernel to JupyterLab. Comparing the blog post to the solution presented by ChatGPT, I thought the AI did well:


> **TV**: how do I add the MATLAB kernel to JupyterLab in kubernetes

> **ChatGPT**:
> To add the MATLAB kernel to JupyterLab in Kubernetes, you will need to follow these steps:
>
> 1. Create a custom Docker image that includes the MATLAB kernel and any necessary dependencies. You can create this image using a Dockerfile that installs the MATLAB kernel and any necessary dependencies, then builds the image.
> 
> 2. Push the custom Docker image to a container registry, such as Docker Hub or Google Container Registry.
> 
> 3. Create a Kubernetes deployment that uses the custom Docker image. This deployment should include a pod template that specifies the image, the necessary environment variables, and any other configuration settings.
>
> 4. Expose the deployment as a service, so that you can access the JupyterLab instance from outside the Kubernetes cluster.
> 
> 5. Configure the JupyterLab instance to use the MATLAB kernel by adding the appropriate kernel configuration file to the JupyterLab instance. This file should specify the name and command of the MATLAB kernel, as well as any necessary environment variables.
> 
> 6. Finally, access the JupyterLab instance using a web browser and verify that you can create new notebooks that use the MATLAB kernel.
> 
> Note that the specific steps for adding the MATLAB kernel to JupyterLab in Kubernetes may vary depending on your specific environment and requirements.

## 3 - Jog your Memory on Code Implementation
This one is pretty straight forward. There will come a time where you are looking a line of code that was written by someone who is no longer on the team or at the organization, and you'll ask yourself: Why?

![Why?](../images/230226-001.png)

Here is another simple example of how ChatGPT can help:

> **TV**: For Python string checking, why might I use `not None` instead of looking for a truthy value

> **ChatGPT**: Using `not None` for checking a Python string checks if the string is defined and not None, whereas truthy value checking only checks if the string has a truthy value (e.g. not "" or 0) which may not be the desired result. The former provides a more explicit check and ensures the string is not only defined but also not equal to None.

You could reach a similar conclusion reading documentation, newsletters, blogs, etc ([this one from Real Python is pretty good](https://realpython.com/null-in-python/)), but getting a concise answer like the one above may be enough to jog your memory on some implementation basics if you happen to be drawing a blank.

Voilà!

## Resources
- [AirBNB Style Guide](https://github.com/airbnb/javascript)
- [ChatGPT](https://chat.openai.com)
- [ESLint](https://eslint.org/)
- [Null in Python: Understanding Python's NoneType Object](https://realpython.com/null-in-python/)
