---
defines: angular
title: 'Angular'
description: 'Angular is a web app framework.'
---

# Programming Environment of Choice

Any software application needs an environment in order to function, i.e. a language which the code is written. The choice of environment is important when designing applications. If the application demands heavy processing then it is appealing to write it in an environment with direct control over a computer's processor, like an operating-system specific approach. With these approaches effort has to be spent on maintaining the environment as computers evolve, and that can be a complicated task. Also the user has to install the software which may end up being a lot harder than it should be.

The other side of the spectrum is to write code in a platform-indepent environment. Doing so inherently loses functionality and performance but greatly simplifies the design process. As computers have gotten more and more powerful the loss in performance becomes less noticable while the simplicity maintains its appeal. Platform-independent environments are appealing for general-purpose applications.

# Web Apps

The ultimate in platform-independent environments is the web browser. Code consists of HTML/CSS/JS and the browser is the environment in which it runs. The internet is inherently platform-independent -- that's kind of the point. Of course there are many browsers out there, each with its own specialties, but there are also rich standards in place which are shared by all major browsers. There is also plenty of documentation available as to which features are available to which browsers, see the [MDN](https://developer.mozilla.org/en-US/docs/Web).

Software written in HTML/CSS/JS which adheres to the standards and common practices (in short, websites) will execute on any device which can be used to surf the web. This is a huge range of users which also happens to overlap with practically all potential users of whatever software is being developed. Having the application built as a website makes it trivial for the end user to set up: all they have to do is navigate to the website and there is the application.

# Making Web Apps

The languages of the web were not designed for hosting applications as websites. They have been greatly enhanced since their inception and it gets easier each year but there's no point denying that raw HTML is inherently cumbersome. It really shines when paired with some kind of helper system to automate generation and interaction with raw HTML.

I have made web apps using vanilla HTML/CSS/JS in the past. Inevitably I would write some JS functionality to automate interaction with the DOM (that is, generation and interaction with HTML). This would usually be one of the first steps since the demand for automation here is so great. But writing this all from scratch for each application is not necessarily a good programming practice. Also there are existing projects which do the same thing but in a more structured and documented manner, and since they have whole teams of supporters they will certainly be more robust than whatever I build on my own.

# Angular

Angular is a framework designed for constructing and deploying web applications. HTML interaction is handled with the use of components which include isolated snippets of HTML designed to present one small piece of the application. JavaScript (or rather, TypeScript) powers the application. And there are lots of pieces of framework for fetching data, transmitting data between components, transforming data, and anything else which is done with data. Program logic also has designated places to live in the framework.

The current version of Angular, Angular 2+, is actually a total redesign of an earlier project called AngularJS. The homemade DOM interaction scripts I was writing earlier more closely resemble AngularJS. Angular (implicitly referring to Angular 2+) is completely different in construction but similar in intention.

Starting Angular is fairly involved. It operates from a command line interface, meaning it has to be installed (along with Node.js and possibly others) on the developer's machine and used from the command line. But there's a reward to this extra work: Angular is split into many small modules and only loads what is required. This makes it perform much better than the monolithic approach of having the user load the entire framework into their browser in order to run the app.