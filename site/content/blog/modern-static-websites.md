+++
date = "2017-04-01"
draft = false
title = "Modern static websites and the benefits"
+++

The process of deploying a website has evolved since I created my first site in the 90's with plain HTML and Apache. I moved on to more advanced sites with PHP (LAMP) and then many other languages and frameworks since then. While monolithic complex servers and databases have dominated the development over the years a combination of the growth in economies surrounding JavaScript with Node/NPM and thousands of web services with API's for comments, forms, email, etc. have brought a surge of modern static site generators in recent years that allow you to make sites that previously required server based code with something like WordPress.

These generators allow you to write blogs and dynamic content, previously requiring something like WordPress, but then compiles it in to pure HTML, CSS and JavaScript which can be served completely from a CDN, like (Netlify)[https://www.netlify.com]. Needs that previously required server-side code can be replaced by web services for contact forms, comments and more. If you need your own API's you can make local JavaScript to use a function that you deploy on services like AWS Lambda for free and which only run when you need them.
