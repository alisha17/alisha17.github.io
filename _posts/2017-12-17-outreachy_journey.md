---
layout: post
title: "My journey of getting into the Outreachy Program"
categories: [outreachy]
comments: true
vertical: Code
author: alisha
image: assets/images/outr.png
featured: true
---


## What is Outreachy?

![]({{ site.url }}/assets/outreachy.png)

[Outreachy](https://www.outreachy.org/) provides **three-month internships** for people from groups traditionally **underrepresented in tech**. Interns are paid a stipend of **$5,500** and have a **$500 travel stipend** available to them. Interns work **remotely** with mentors from Free and Open Source Software (FOSS) communities on projects ranging from **programming, user experience, documentation, illustration and graphical design, to data science**. Interns often find employment after their internship with Outreachy sponsors or in jobs that use the FOSS skills they learned during their internship.

Outreachy internships are open internationally to women (cis and trans), trans men, and genderqueer people. Internships are also open to sresidents and nationals of the United States of any gender who are Black/African American, Hispanic/Latin@, Native American/American Indian, Alaska Native, Native Hawaiian, or Pacific Islander.

## How I ended up being an Outreachy Intern at Fedora?

I first heard of Outreachy through a friend in 2015. But at that time, I had just completed my undergrad and was not confident of myself AT ALL, which is really justifiable, since you cannot think of working for top-notch organizations/communities like Mozilla, Fedora, Linux, Wikimedia and many more..

### Getting started with open source

However, I was really intrigued with the idea of Free and Open Source Software (FOSS). Hence, I decided to make some contributions towards it.
Mozilla is an organization that everyone must have heard of since childhood. Atleast I am using Firefox from the time I first started using computers. Fortunately, I have a friend who was already a contributor in Mozilla automation and tooling projects. She introduced me to a Senior Engineer working at Mozilla. He mentored me and helped me in making my first contribution. In a span of one year, I contributed to Bedrock, Firefox, Treeherder and Taskcluster and have around 35 merged PRs into the codebases.

### Outreachy round 14: Disappointments

I decided to apply for Outreachy round 14 (June-Aug'17); for which the applications open in February.
There were some many awesome organisations and projects. I was already familiar with how Mozilla's bug tracking system works (using Bugzilla), how to open PRs and how the reviews work etc. I chose 2-3 projects which I found interesting. I made contributions to all of them, but
ultimately the project which interested me the most was **Rust Web Assembly Showcase**. The mentor of the project was **Brian Anderson (co-creator of Rust)**. The task of the project was to create a web application in Rust and compile it to Web Assembly.

I started fixing some Rust bugs and making small Rust applications all compiled to Web Assembly. It was so much fun! Brian shortlisted me as the Outreachy intern for his project.

**But then this happened.....**

A week before the selected Outreachy interns were to be announced, I received a mail from the organizers informing me that I was not eligible for the internship since I did not have full 3 months off from the university, and the Outreachy eligibility criteria clearly states this. Though, I had like full 2 months off, but the academic calender did not explicitly asserted this. Me and Brian tried to convince them, but probably they were right as they did not want the intern's studies to suffer. Brian was disappointed too (since I had already started working on the project) and I was very disheartened, but that did not deter me from working harder and learning Rust in the process. Brian, being an awesome Rust community member, still mentored me all through the summer like he would mentor an intern and I ended up doing two Rust projects: [Tic-Tac-Toe](https://github.com/alisha17/tic-tac-toe) and [Testrunner](https://github.com/alisha17/testrunner). **[Thanks Brian!]**. We had weekly Hangouts and IRC meetings, code reviews, bug fixes and it was a great learning experience. I even completed the [Rust Libz-Blitz](http://blog.rustfest.eu/libz-blitz) contest and won free tickets to Rust Fest Switzerland, but I wasn't able to go anyway (That's a story for another day! :-p)

### Outreachy Round 15: Finally!
I was really excited for Outreachy Round 15 (Dec'17-March'18) and was determined to apply for it.
There was no Rust project this time but I found another interesting project to apply for which was Fedora's **Developing administrative tools for 389 Directory Server** and the mentor was **William Brown (Software Engineer, Red Hat AU)**. Fedora is a Unix-like operating system based on the Linux kernel, developed by the community-supported Fedora Project and sponsored by the Red Hat company and the 389 Directory Server is an enterprise-class Open Source LDAP server for Linux. It handles many of the largest LDAP deployments in the world. The basic task of this project was to improve the Directory Server's python command line tools.

##### Why I found this project interesting?

* **LDAP** - Anyone who has any acquaintance with LDAP will understand my bittersweet love for it. It has a very steep learning curve but is interesting as hell. Its structure and schema is nothing like your conventional databases. Moreover, there are not much learning resources online, so you have to explore and read the codebase to understand deeply. So, what can be the best way of learning a new thing than actually working on it, because no amount of learning from online resources can beat practical experience with the help of an awesome mentor!

* **Python** - I just love Python. I already program in Python and more the experience, the better it is.

* **Community** - I have had experiences with some open-source communities which were not good at all. So, community matters a lot for me. You don't want to feel scared while asking things from the community.

I started contributing to this project and it was so exciting! Even in the process of fixing some bugs which was essential for submitting the application for Outreachy, I learnt a great deal (setting up the Directory Server, setting up Apache Directory Studio, LDAP concepts etc.). I got selected as an Outreachy intern for this project and now I am working on it! :)

William is an amazing mentor as well as an amazing community member. He is always so supportive and provides guidance and explains each concept very thoroughly with patience. I can not imagine working without his direction. **[Thanks William!]**

The journey wasn't easy but was worth it. Even the little bug fixing and contributions for applying for the internship teaches you skills such as time management, especially if you are a student like me.

## Some tips for Outreachy aspirants:

### CHECK THE ELIGIBILITY CONDITIONS, I REPEAT, CHECK THE ELIGIBILITY CONDITIONS!
You don't want to get disappointed only to be notified later that you are not eligible, after putting in a lot of time and effort and as a result shattering all your hopes! I was really paranoid about the eligibility when I was applying this time. I checked maybe 50 times :P

### CHOOSE PROJECT THAT INTERESTS YOU
You don't wanna do the project just for the sake of getting selected as an intern. Remember, you will be doing this project for 3 months full-time. So, it should actually excite you!

### GET STARTED WITH VERSION CONTROL SYSTEMS LIKE GITHUB
This is very essential as almost all open source repositories use some king of version control systems like github or their inhouse systems like Fedora uses Pagure, but the essence is the same. If you know how to drive a car, you can drive any car. So, maybe start with using Github, learn about the basic commands (push, pull, commit etc.), push your local projects, play with using git from CLI etc.

### START CONTRIBUTING AS EARLY AS POSSIBLE
I was already an open source contributor from past 6 months when I applied for the first time for Outreachy and I was familiar with  how things like Pull Requests, Patch Reviews, Bug Filling, Bug fixing etc. worked. If you start with these things during the Outreachy application period, you will spend more time understanding these and subsequently, you will get less time to work on the actual project.

### COMMUNICATION MEDIUMS - IRC, SLACK
Probably IRC is the most common open source communication medium. Communities like Fedora, Mozilla, Openstack use IRC. It facilitates communication in the form of text and is based on client-server communication. Read about how IRC works and setup a client for it. I use [Hexchat](https://hexchat.github.io/) for IRC and it works like a breeze.
Slack is pretty popular these days and getting started with it is as easy as creating an account and start talking. You can also download the Slack iOS or Android app to always remain updated.

### RESPECT YOUR MENTORS
I consider myself lucky as I have always had amazing mentors. But remember, they are also human beings. By mentoring you, they are putting double the efforts (as most of them are full-time employees as well). So:

* Respect their time, do not bug them too much.
* Talk to them politely (mails/slack/IRC). Use the magic words, 'sorry', 'please', 'thankyou'.
* Be honest with them. If you don't know something, **ask** them. They are there to help you.
* Be in touch with them and talk about your progress regularly.

### ASK QUESTIONS, A LOT!
The more you ask, the more things become clearer. Don't be afraid to ask. The mentors and the community will help you. Most of the mentors are really passionate about their projects and will genuinely want you to learn more and more.

### TIME MANAGEMENT
This one is probably useful during the application process. If you are a student like me, you will have to juggle studies and exams with bug fixes/understanding the projects etc. This was my routine during the application period: Morning till evening studying and attending classes at the university, then I used to come home around 6.30, have my meal and sleep for like 1 hour. Then from 8 till 1 am, I used to work on the project. I am quite focussed at nights :)


## Any Questions?

If you have any questions about the Outreachy program, application process, Mozilla, Fedora, github, IRC etc. etc., don't hesitate to drop me a mail or connect with me on Twitter/LinkedIn!

Thanks! :)

