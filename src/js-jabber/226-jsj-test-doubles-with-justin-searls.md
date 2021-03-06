---
layout: layouts/post.njk
title: >
  226 JSJ Test Doubles with Justin Searls
date: 2016-08-24 07:00:25
episode_number: 226
duration: 01:04:11
audio_url: https://media.devchat.tv/js-jabber/JSJ226TestDoubles.mp3
podcast: js-jabber
tags:
  - js_jabber
  - podcast
---

## [React Remote Conf](https://allremoteconfs.com/react-2016) and [Angular Remote Conf](https://allremoteconfs.com/angular-2016)

&nbsp;03:15 - Justin Searls Introduction

- [Twitter](https://twitter.com/searls)
- [GitHub](https://github.com/searls)
- [Blog](https://about.me/searls)
- [Test Double](https://testdouble.com/)
- [JavaScript Jabber Episode #038: Jasmine with Justin Searls](https://devchat.tv/js-jabber/038-jsj-jasmine-with-justin-searls)
  04:13 - Testing
- [testdouble.js](https://github.com/testdouble/testdouble.js)
- [teenytest](https://github.com/testdouble/teenytest)
- [Sinon.JS](https://sinonjs.org/)
  08:44 - Mocking
- [Growing Object-Oriented Software, Guided by Tests by Steve Freeman and Nat Pryce](https://www.amazon.com/Growing-Object-Oriented-Software-Guided-Tests/dp/0321503627)
- [Jim Weirich](https://en.wikipedia.org/wiki/Jim_Weirich)
  14:45 - Starting These Concepts as a Junior Developer
- [Test-driven Development](https://en.wikipedia.org/wiki/Test-driven_development)
  17:55 - [testdouble.js vs. sinon.js](https://blog.testdouble.com/posts/2016-03-13-testdouble-vs-sinon.html)
- [NIH = Not Invented Here](https://en.wikipedia.org/wiki/Not_invented_here)
  26:39 - [Duck Typing](https://en.wikipedia.org/wiki/Duck_typing), [Monkey Patching](https://en.wikipedia.org/wiki/Monkey_patch), Duck Punching32:22 - [Node.js](https://nodejs.org/) Negativity
- Design, Resources
  - Martin Fowler’s Refactoring and Patterns Books
  - [Domain-Driven Design: Tackling Complexity in the Heart of Software by Eric Evans](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215)
    42:52 - Community45:08 - The AAA Rule: Arrange, Act, Assert51:19 - Error Messages&nbsp;Picks
- Unemployment (Jamison)
- [React Rally](https://reactrally.com) (Jamison)
- [Julia Evans' Tweet: how to be a wizard programmer](https://twitter.com/b0rk/status/755020037979856896) &nbsp;(Jamison)
- See the good in people (Aimee)
- [Sinon.JS](https://sinonjs.org/) (Joe)
- [How to Stay Motivated: Developing the Qualities of Success by Zig Ziglar](https://www.amazon.com/How-Stay-Motivated-Developing-Qualities/dp/B001E4SMKG) (Chuck)
- [The Harry Potter Series](https://en.wikipedia.org/wiki/Harry_Potter) (Chuck)
- [RetroPie](https://retropie.org.uk/) (Justin)
- [How Elm can Make you a Better JavaScript Programer](https://opbeat.com/events/web-rebels-2016/#elm-can-make-you-a-better-javascript-developer) (Justin)
- [NEJS Conf](https://nejsconf.com) (Justin)

### Transcript

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle's been working with Angular 2 for a long time and they are now putting together an eight-hour, 2-day course designed to help Angular developers learn how to write apps in Angular 2. If you're looking to level up your JavaScript and Angular 2 skills then go to Rangle.io/training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that available at Rangle.io/training.]_**

**_[This episode is sponsored by Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to try debugging issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install and you could start tracking production errors and deployments in eight minutes or less. We have a special offer for JavaScript Jabber listeners. Go to Rollbar.com/JSJabber and sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked for free. Loved by developers at awesome companies like Heroku, Twilio, Kayak, Instacart, Zendesk, Twitch, and more. Give Rollbar a try today. Go to Rollbar.com/JSJabber.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 226 of the JavaScript Jabber Show. This week on our panel we have Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** Jamison Dance.

**JAMISON:&nbsp;** Hello, friends.

**CHUCK:&nbsp;** Joe Eames.

**JOE:&nbsp;** Hey, everybody.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Quick shout-out about React Remote Conf and Angular Remote Conf coming up in October and September. We also have a special guest this week and that is Justin Searls.

**JUSTIN:&nbsp;** Hi everybody.

**CHUCK:&nbsp;** Do you want to give us a quick introduction to who you are?

**JUSTIN:&nbsp;** I would rather make Jamison Dance introduce me. [Laughs]

**JAMISON:&nbsp;** I'm going to introduce Justin. Justin is the foremost Rubyist in the JavaScript scene.

[Laughter]

**JAMISON:&nbsp;** Justin… I'll do a better job. Justin runs a consultancy called Test Double which is always hiring. He talks at a lot of conferences and he gives fantastic talks. I've really enjoyed the talked of his that I've seen. And he cares a lot about testing. I feel like you write and speak a lot about testing. Other things too, but a lot of it around testing, [how to be] better at testing and how to not be worse at testing which sound like they're two different things, kind of. Is that an okay intro?

**JUSTIN:&nbsp;** Thanks. That was humbling.

**JAMISON:&nbsp;** [Laughs] Like in a good way or a bad way? [Chuckles]

**CHUCK:&nbsp;** [Laughs]

**JUSTIN:&nbsp;** I think that you are really good at doing intros and you're not bad at doing intros, Jamison.

**JAMISON:&nbsp;** Oh, thank you.

**JUSTIN:&nbsp;** [Inaudible] pretty good to me.

**CHUCK:&nbsp;** So, we've had you on the show before, Justin. I don't recall what exactly we talked about then but this time we're going to be talking about testing.

**JAMISON:&nbsp;** It was Jasmine.

**CHUCK:&nbsp;** Oh, was it Jasmine?

**JUSTIN:&nbsp;** I do recall.

**JAMISON:&nbsp;** Yup, talked about Jasmine. I remember that one.

**CHUCK:&nbsp;** Well, we're still talking about testing. We're talking about testdouble.js and teenytest. I read your article that explains what testdouble is and compares it to Sinon. I have to admit, I don't know if I followed all of it. So, why don't you give a brief overview of what testdouble is? And then we can start asking questions and talking about the approach that it takes and why people may, depending on their philosophy about testing, prefer one tool over the other.

**JUSTIN:&nbsp;** Yeah, right. So, here's a pro tip to everyone in the audience if they want to rise to prominence in whatever software community they're in. and that is find an area where people don't care very much about stuff and then choose to care a lot about that. Obviously building code that's also in production is everybody's job so everybody cares a lot about that. And it's really hard to make a name for yourself on that. And the last time I was on this show it's because I was working really hard to try to improve the state of testing for frontend JavaScript. Node.js wasn't really a significant force then. And I found it difficult to communicate the importance of or the relevance of a secondary thing that is its own entire school of thought with tons of jargon and complexity to people who just, for them it's you know, testing is important but it's obviously secondary to getting stuff done.

When we talk about mocking frameworks or mocking libraries or test doubles or stubs or spies and all of the words we use to just mean fake thing in a test, that's not a particularly nuanced aspect of testing. That's really if anything a tertiary concern for almost everybody. And if anything, I've just lasered in on this one particular problem domain for no other reason other than my own dissatisfaction with mocking libraries first in Java and Ruby and now in JavaScript. It's just… something's been stuck in my [inaudible] for years over it. And so, I care a lot about it. But I understand at the same time that most people listening to the show may not have any idea what a mocking framework is even if they write a lot of tests. A lot of others will have discovered one and the most dominant one in JavaScript is called Sinon or Sinon.

**JAMISON:** I have [inaudible]

**JUSTIN:&nbsp;** [I don't think] we have a formal pronunciation? Jamison and I were actually in Oslo, Norway last month and several of the original author's coworkers were there. And I was asking them, “How do you pronounce this thing?” And they tried to get me an official answer but I still got four different answers for how to pronounce it. So regardless, Sinon is the incumbent test double library for JavaScript as it gets millions of downloads every month. And I've always been frustrated by it.

First, to tell you what a test double library even sets out to do is when you're testing stuff, oftentimes having everything be real is not ideal. Maybe you're trying to write an integration test that focuses just on your code but not necessarily on the services that it depends on. Or maybe you're trying to do isolated unit tests where you're testing just a particular function and you want to verify the interactions that that function has with the things that it depends on as opposed to actually making sure that the whole thing works. A lot of people who practice test-driven development want to get that so that they can get better design feedback from their tests. And so, those are the two primary motivations for why you'd want to fake out something when you're writing a test.

And Sinon, Sinon, I'm just going to keep making up a new pronunciation every time I say it.

**JAMISON:&nbsp;** That's good.

**JUSTIN:&nbsp;** I feel like it's…

**CHUCK:&nbsp;** Swirly.

**JUSTIN:&nbsp;** Swirly? I feel like it's less thoughtfully designed than the leading or dominant test double libraries in other languages. The API is confusing. It's all over the place. It mixes up jargon like stub and spy and it's not very formal about them. It mutates a bunch of stuff without really asking. It's difficult to reset global state. It has this chainable API but it's still really hard to do a lot of very common things as one-liners. And I saw all those problems and I just kind of bit my lip for three years until we got enough at Test Double project experience of people helping teams, large teams that are writing a lot of tests again and again find that they don't understand how to use test doubles or mocks well. And they don't even really understand what they're accomplishing. And a big part of that was that they found that the Sinon API was fighting against them. It wasn't really helping encourage proper use. And I…

**JAMISON:&nbsp;** Can I…

**JUSTIN:&nbsp;** Go ahead.

**JAMISON:** Can I ask you to do a brief… I know this is another gigantic, enormous, [inaudible] complex topic. But can you do a brief aside into the right way to mock things out versus ways that might cause you pain? Because I know that, I've heard stuff about the dangers of over-mocking and how that can make your tests really brittle and lead to some negative consequences. But what is the right to do that? Is that something you can talk briefly about?

**JUSTIN:&nbsp;** Oh man, for sure. I could also talk long-ly about it.

**JAMISON:&nbsp;** Yeah, yeah. [Inaudible]

**JUSTIN:&nbsp;** Like I'm sure I just did about mocks. Sorry for that. And this is exactly the kind of risk, right? Is I'll just talk over everybody's heads because this is something that is really complex.

**JAMISON:&nbsp;** Yeah.

**JUSTIN:&nbsp;** But to break down as simply as I can, I think it gets back to what I was saying earlier about there being two motivations for wanting to fake something out in your tests. One motivation is I want to test this but not everything can be real. Maybe some of those services are too slow or maybe I want to be able to run my tests offline. Or maybe I don't know what. Maybe it's just a pain to get this test to work and it would be a lot easier for me to write this test if I could fake out that object or this function. And…

**JAMISON:&nbsp;** So, like the test needs a database connection or something and you just want to [inaudible].

**JUSTIN:&nbsp;** Yeah. And that's sort of the classical example. And maybe people start there. But then, because it's a powerful thing to be able to just fake out reality, right? It becomes a golden hammer for a lot of teams. And so, they just sort of as a tool of convenience start mocking stuff out willy-nilly but without a really governing principle over it. And that's where I think you get into discussions of over-mocking. Now, keep in mind too that when I said that there are two motivations, we're still on the first one and it probably represents 99% of how people tend to use mocking libraries. Because they're very convenient. They solve a very immediate need.

But when you use them in a way that isn't particularly disciplined you just end up with a bunch of tests that have some amount of decreased confidence. Like I am less, as I mock more and more stuff I am less and less certain that the thing I am testing is behaving the same way in my tests under the same conditions as it would in production. And that's where people start to hate on it, right? They can't trust the tests. They don't understand the purpose of the test. They don't know what's real and what's fake. When it breaks they don't know how all of the test doubles are set up to go in and fix it. That's the first category. Does that make sense? Of test double use.

**JAMISON:&nbsp;** Yeah.

**JUSTIN:&nbsp;** And in general, I said 99% uses that category. The other 1% of use is people making all the test double libraries. They're people who care a lot about isolated test-driven development. So, if you go back and you like at for Java there is Mockito or jMock, Ruby had FlexMock early on or Mocha, the authors for all those were trying to facilitate isolated test-driven development. Back when we were in Oslo, I did a new talk to try to illustrate what that looks like.

But at a high level it means say I'm doing a new Express route. And it's a controller. And I want to use a test to help tell me how to break that problem down. So, if I'm doing three things and I know the controller needs to do three things, rather than just write a test and then try to solve everything, I'll think upfront, “Hey, how could I break this problem down? I wish I had maybe something that went and fetched items and then something that transformed those items into data that I can, third thing, send off to a service?” So, I'm going to create three fake things to represent those three responsibilities, write a test, wire it up, make the test pass. And now I've got three smaller problems. And that's how I actually use test doubles. And the patterns of how you use them in what features you need are a little bit different.

So, you end up with a very opinionated API that has a very clear story to tell about how it's supposed to be used. But unfortunately we don't have really great marketing from the perspective of why this is a valuable approach to building software. And it gets mucked up with the complications of people who genuinely just need mocks just to fake stuff out. And I think that's really the tension that we've been dealing with all this time.

**JAMISON:&nbsp;** Sure. So, that second approach you talked about is kind of, is that something you'd see in the book 'Growing Object-Oriented Software'?

**JUSTIN:&nbsp;** Yes, absolutely. That was the genesis of it all.

**JAMISON:&nbsp;** Okay. That makes sense. Thanks for answering my tangent question.

**JUSTIN:&nbsp;** Not a tangent at all, to be honest. I think it really cut to the heart of the issue. Some people may have heard of the book GOOS. It's been called outside-in testing, isolationist testing. Martin Fowler calls it mockist testing. I started calling it discovery testing because I figured it we just keep throwing labels at a wall maybe one will finally stick.

**JAMISON:&nbsp;** Someone's going to get famous and it's going to be the person that invents that label that sticks.

**JUSTIN:&nbsp;** Right, exactly. [Inaudible] testing.

**JAMISON:&nbsp;** And you [inaudible] made out of discovery testing.

**JUSTIN:&nbsp;** Yeah, right. That's the goal anyway. I don't know. I just talked a great length and relatively granular level of detail. Does anyone have experiences that they can share about mocking or Sinon that might be pertinent?

**JOE:&nbsp;** It's awesome?

**CHUCK:&nbsp;** [Laughs] Yeah. I mean, when I was learning how to write tests, granted this was in Ruby, but I sat down. The first person I asked about mocking and stubbing was Jim Weirich who wrote FlexMock in Ruby. And as I came to understand it basically yeah, I would use mocks to isolate or basically to make it so that I don't have to worry about the particular parts of whatever I was testing that weren't core to what I wanted the test to be about. And yeah, I found that it simplified a lot of things. Because then it was, “Okay, I don't have to care if the service is down or the API server is down. I don't have to care if the database has the right data in it.” Because I can basically tell something, “Act like the database and just give back the data I want.” And then occasionally I would also get into the places where it was like, “I need to know that this was called,” because it was just mission critical that that particular API was called. And again, it just simplified things. It made things easier to keep track of. And that's where I really like mocks.

**AIMEE:&nbsp;** I wanted to back up too, and I always like to get your advice or opinion on newer developers. Because I know, so for me when I first learned how to do testing, I really didn't' start with mocking and stubbing because I think the process of learning how to test your code when you are very, very, very new, that's kind of mind-boggling in itself first. And so, when you start adding how to do an actual proper test by mocking things, like if you're not doing just, if you need to mock out things that your actual test needs it can get overwhelming. So, at what point do you think it's good to start actually using those things?

**JUSTIN:&nbsp;** I think that it's very easy when you're new to succumb to the power of the tools that you have in front of you and try to mix in a whole lot of stuff all at once.

**AIMEE:&nbsp;** Yup, yup, exactly.

**JUSTIN:&nbsp;** And then get overwhelmed because you know how to do a lot of stuff but you definitely don't understand how it works.

**AIMEE:&nbsp;** Yup.

**JUSTIN:&nbsp;** It very quickly, you can, the why you're doing what you're doing can slip away, right?

**AIMEE:&nbsp;** That's my favorite thing I like to bring up. Exactly.

**JUSTIN:&nbsp;** So, we don't want that, right? And I think that the best developers I know are the thoughtful ones who never do anything without knowing why they're doing what they're doing. And what I would recommend is to get, if you're new to testing start by writing really realistic tests. Tests that call through your whole system just like a real user would use it. So, if it's a browser application start with tests that automate browsers. If you're building a little module that talks RESTfully to other web services, write a client that will talk to it over HTTP and then test it that way. And that way, you're getting very valuable experience because you're learning how to structure tests in a way that does the setup, invokes the thing, verifies the behavior reliably, and hopefully consistently focusing on consistency, focusing on organization, keeping stuff relatively simple. But everything that you do in that case will be valuable because out the other end you're going to have a test that you're pretty confident actually exercises the thing like reality because you're keeping everything pretty real.

Where I'd encourage people to start looking at a library like testdouble or Sinon is probably if they start to learn test-driven development. And if you want to get into test-driven development, my biggest objective typically when I'm teaching somebody is to encourage them to focus on design. You're writing a test of a new thing that doesn't exist yet? Try to imagine what things you wish it… if these things that don't exist, if they existed they could do my job for me so much more nicely, then this test that I'm trying to actually write now would become easy. And using mocks can be a great sounding board for developing those things. And there's a whole discipline and it certainly is not something we can solve over audio and explain in great detail. But that's probably the moment where I'd encourage somebody to cut their teeth on mocking libraries. As opposed to bringing it into an existing set of integration tests and just sort of using it as convenient. Because then you end up with very inconsistent use and I found that inconsistency is typically the biggest root cause of frustration that people have with test suites.

**AIMEE:&nbsp;** That's a good answer. Good advice.

**JUSTIN:&nbsp;** So Joe, you're a big fan of Sinon. But I know that you took at least a minute to check out testdouble in advance. How would you compare the two so far?

**JOE:&nbsp;** Actually I was really impressed with what you did with testdouble. I've spend a ton of time, I'm going to have a hard time coming up with your alternate. I've always pronounced it one way. So, I'm going to, maybe I should do something completely wacky. Sinon. How about that?

**JAMISON:&nbsp;** that was my alternate.

**JOE:&nbsp;** Oh.

[Laughter]

**JOE:&nbsp;** Sinon. I'll go with Sinon. You can have Sinon.

**JAMISON:&nbsp;** Okay. I'm happy to share my alternate with you too.

**JOE:&nbsp;** [Laughs] I'll end up just calling it Sinon all the time. But I've got a lot of experience with Sinon. I was really happy to discover it when I first came over to the JavaScript world because I was a huge TDD-ist long before I ever started frontend development back in the early 2000s. So, I was really happy to have Sinon available to do all this sort of stuff and really liked the API. And then I read your article. And I'll be honest when I first saw that you had written this article about testdouble.js, my first initial reaction was, “Well, this is probably just going to be your own oh I like red instead of blue. I like apples instead of oranges. So, I've coded this up to be my flavor. I like this flavor but not the other flavor and that's what this is for.” But I was a lot more impressed at the thought that you gave through the API.

And you actually point out a lot of problems with the Sinon API that I've never truly noticed before. Maybe it was, I don't want to call it Stockholm Syndrome by any means. But you use a product, if it's the only product available. The only real mocking library that was out there that you can use at all is Jasmine's spy library, right? And a few people use that and it doesn't have a lot of features to it. It's very limited. So, it's okay, but Sinon was far more feature complete so I just got very used to Sinon even though I have experience with a lot of server-side language test mocking libraries, various ones, and I've seen a bunch of different kinds of APIs. So, I'm definitely opinionated on the matter. But maybe it was the only game in town and so I got very used to it. But reading your article I've seen a lot of intelligence and thought going into, “Hey, there are ways to make this better.” Your points about how the chainable API can actually cause problems because you can very easily conflict with what you'd earlier done in the chain and then it becomes very confusing as to what's going on.

So, I was really impressed with testdouble.js and thought this is actually, and without spending significant time with testdouble.js it looks to me like a next step forward.

**JUSTIN:&nbsp;** Well, that's very kind of you. And I appreciate it. I think what I'd say is if a lot of thought went into testdouble it's probably because I first had to foist upon the world a bad mocking framework for Java and then a bad mocking framework for Ruby. And I learned a lot of lessons about what at an implementation level it might look like. But the biggest thing I learned in trying to get people on board with them is that people have patience for rough edges around production dependencies they're going to use a lot. Express has some quirks in its API. And people will suffer that because they need it. They use it.

But what I've found is that with like I said a tertiary concern like mocking, people aren't just willing to devote the head space to understand really what's going on beneath the covers much less deal with the nuances presented by in the instance of Sinon a really, really gigantic surface area of its API. The number of different permutations and ways that you can do things are very, like you said, I think problematic. And for most users they don't actually experience that because they only interface with it at a very thin level. And it actually does have a lot of power. You can do a lot of things with it. But it makes it hard to find those things, especially things that you might need to do frequently.

**JAMISON:&nbsp;** Right. I want to give input as a…

**JUSTIN:&nbsp;** That's the goal. I was [trying to] popularize these ideas with testdouble.

**JAMISON:&nbsp;** I want to give input as a novice user of Sinon. I have been overwhelmed and felt the constant fear that I'm doing something wrong because I'm using four functions out of the 8,000 that it had or something. And I'm not super well-versed in mocking or the theory of it. So, I'm kind of counting on the library to guide me. And I just don't know. I'm like, I must be doing something wrong because I'm not using very much of it.

**JOE:&nbsp;** Right, yeah. Like I feel like I'm not a very good target audience to judge because even though I worked a ton with Sinon and I have a lot of exposure and experience with testing, I really don't represent the majority of people who are going to use a mocking library which is people that like you said, it's a very tertiary concern. I need to get this thing done. In order to get this done I've got to use this technology and I don't want to spend a month learning it. For me I was more than happy to dive into Sinon and learn every nuance and little bit. And I was able to compare it to something I already knew somewhere else. Whereas for somebody who just wants to quickly figure out how to do basic tasks and move forward, it's a very big, a very complex product.

Now, that being said I also felt like it was a great product. And I still feel like it's a great product. It's very feature complete. The documentation is pretty reasonable, especially for a project that's mostly handled by one guy. So, it's a great product but I like that you're taking another iteration on the whole idea and saying, “Alright, well let's approach this.” And I also feel like again, you have so much experience it's easy to get lost in the details and in the forest and create something that's easy for somebody who is highly experienced and an expert in the topic. Instead it looks to me like you've created something that's going to be easy for people to onboard with. And my first experience with a mocking library if it's this thing, if it's testdouble then it's actually going to be smoother than it could be.

**JUSTIN:&nbsp;** Yeah. Jamison to your point, I think that opinionated libraries tend to be superior to un-opinionated ones because they have the kind of focus to not let feature creep come in. the documentation is a lot easier to write when the author has very strong opinions. I've actually, I really struggled with Sinon's documentation to be honest. And the whole thing that led to me writing testdouble is I was struggling to figure out how to use it despite having a lot of experience. And so, I'll link for you guys the documentation for testdouble. It actually does go really, really deep in-depth. And the intention isn't necessarily that you have to go read that right now because there is the TL;DR at the top. But just to make sure for people, they understand why I'm doing what I'm doing all of the different options that are available so that it's really searchable, I want to make it really easy to master this stuff. Because I feel like there's just not enough people who've been given the opportunity to really understand mocking well yet, especially in JavaScript.

**JAMISON:&nbsp;** So, can I bring up a thing I've encountered. For me, the choice whether to use Sinon or not was like, is it easier for me to just write a stub to [a] function myself and set some value inside the closure it creates. Can you talk about when you decide to use a library versus when you just change things yourself and then change them back? Does that question even make sense?

**JUSTIN:&nbsp;** Yeah. I think the terminology in Agile land where I came from originally would be to roll your own mocks, so to speak. Because I have this library now that's really like, I like to say lightweight because it doesn't really have any meaning. It's just like a general positive word [you can use for JavaScript].

**JAMISON:&nbsp;** It just means good, yeah.

**JUSTIN:&nbsp;** Yeah, yeah.

**JAMISON:&nbsp;** [Lightweight] is good if you [inaudible] JavaScript.

**JUSTIN:&nbsp;** Yeah, it's just a humble brag.

**JAMISON:&nbsp;** Modular. Say modular.

**JUSTIN:&nbsp;** Super modular. Because testdouble is easy to slot in, easy to use. And if you call reset once you're confident you're not going to accidentally muck with any global state. I would use it all the time but I think that where a lot of people who roll their own mocks like that strategy is that, like we said earlier, they can definitely understand everything. And if they're really consistent about how they write and structure all their tests, they probably won't end up writing some gigantic massive regime of test helpers and fake mock stuff. Because I'm all about local fakes where that helps add clarity to the tests. I just feel like I'm always pushing against NIH especially when we're talking about testing. And for listeners who don't know NIH it stands for Not Invented Here. People reinventing wheels.

**JOE:&nbsp;** Well, and I think that testing is a little bit complicated by the fact that in JavaScript specifically due to duck typing and monkey patching you can do a lot of the faking very easy as long as you have a rudimentary understanding of JavaScript. So, you might get really, really far writing your own mocks. But a mocking library has so many features that you're missing out on you can often not realize what you're missing out on.

**AIMEE:&nbsp;** Hey Joe, can you actually define those for people really quick in case they don't know?

**JOE:&nbsp;** Sure. Duck typing is the idea that if it looks like a duck and walks like a duck and quacks like a duck, it's a duck. So, in JavaScript if I have an object that has a property name and I'm expecting an object that has a property name and age and I'm going to feed it into some function that requires both a name and an age, all I had to do to the object that already has a name to make it work is give it an age and add an age property to it. And now because it has a name and it has an age, it's going to work just fine in the function. And other more strictly typed languages like say C# or Java, you're relying on the type of I create an instance of a class A and I create an instance of class B and they both have the same properties, if I'm expecting class A even though class B has the same properties, its' not going to work. If both class A and class B have name and age and I have a function that expects class A and instead I give it a class B, it's not going to work, right? So, that's not duck typing. In JavaScript, so long as the object that you're feeding in has all the properties that the function or algorithm expects, JavaScript works just great. So, that's duck typing.

And then monkey patching is in JavaScript specifically, that's the ability to go in and add more functions to an already existing object. I don't know, [inaudible] has a better explanation for monkey patching if anybody has one.

**JAMISON:&nbsp;** I know that's a thing that happens a lot in Ruby. So, maybe Justin can give us an idea of that.

**JUSTIN:&nbsp;** [Laughs]

**AIMEE:&nbsp;** Yeah, it was definitely for me the first time I heard those words was when I was doing Ruby.

**CHUCK:&nbsp;** Yeah, but it's definitely something that you can do in JavaScript as well where you effectively open, in this case it's not a class but you can open a function's prototype or open an object and add or modify what the functions or what the properties are.

**JOE:&nbsp;** Right. You could actually modify existing functions which is kind of an aspect of monkey patching.

**CHUCK:** In the middle of a running program.

**JOE:&nbsp;** Right, exactly. And then also…

**JAMISON:&nbsp;** Just like monkeys do. Hence the name monkey.

[Laughter]

**JOE:&nbsp;** Right. In the middle of running programs, that's what they do.

**JUSTIN:&nbsp;** Yeah, even though… I don't know if it's still around but I remember when Underscore was just starting to become a thing. I think it was called Sugar.js was kind of a similar project except what it did was monkey-patched the prototype of all of JavaScript's built-ins like number and array and string to try to either add additional functionality or clean up cross-browser quirks. And that's all well and good unless you pull in some third-party code that doesn't assume that string and array have been monkeyed with. Hence all the monkey references. I will mention though…

[Chuckles]

**JUSTIN:&nbsp;** That the first time that I discussed monkey-patching with somebody who was a Node.js developer they used the term duck punch. And I kind of, that one's grown on me.

**JAMISON:&nbsp;** I think that's a Python thing, right?

**JOE:&nbsp;** Yeah. I heard Paul Irish use duck punching in a talk that he gave. But you know, monkey patching also kind of has a grown-up cousin to it which we call polyfills and shims. Basically kind of the same thing.

**JAMISON:&nbsp;** That's true. Yeah, I haven't thought of that. Monkey patching is what you call it when you want to make fun of it. And polyfill…

**JOE:&nbsp;** Yes.

**JAMISON:&nbsp;** Is what you call it when it makes your program work.

**JOE:&nbsp;** Right. [Laughs]

**CHUCK:&nbsp;** Well, yeah I've seen monkey patches that make programs work. But the problem with monkey patches is because you've done it at runtime in the middle of the running program and you've made these changes, you may make changes that don't then meet the assumptions that other people or other parts of the program have for that particular object or function.

**JOE:&nbsp;** Right.

**CHUCK:&nbsp;** And so then when they call it and they pass in something that they assume should be an integer for example and you've monkey patched it so it accepts a string, and it can't be properly coerced, then you got a problem. Or…

**JAMISON:&nbsp;** But if it can be properly coerced then you've polyfilled it. And you've done [inaudible]

**JOE:&nbsp;** [Laughs]

**JUSTIN:&nbsp;** Yeah, Jamison's got the right marketing mind here. You know, [inaudible].

**CHUCK:&nbsp;** Yes. Yes, he does. But…

**JAMISON:&nbsp;** I'll [inaudible] made out of polyfills.

**JUSTIN:&nbsp;** Yeah. When I want to criticize I call it a mocking framework. And when I promote my thing I call them test doubles.

[Laughter]

**JUSTIN:&nbsp;** Because mock is such a negative word.

**JOE:&nbsp;** Right. So, to go back to those two terms, duck typing and monkey patching or the more fun duck punching, because of those aspects of JavaScript, the fact that you can take an existing object and modify its properties, its methods at runtime, you can easily take an algorithm that expects to receive some object and then call a method on that object. And maybe the object that you're going to pass in is like your database API or your HTTP API. So, when it makes this call in this function it's supposed to actually call across and make a web call and instead you pass in an object that just has an empty function instead of a function that will really call, make in an HTTP call.

So, it's very easy to by hand say, “Oh, my algorithm expects to pass in, to bring in this HTTP object. I'm just going to pass in my own object that looks like it,” at least as far as the algorithm is concerned. Because maybe the original, the full HTTP object has 20 methods and 15 properties but my function only calls one method on it. So, I only need to pass in an object with that one method which is duck typing at its finest. So, it's easy to do this by hand whereas in a language like C# or Java its tons, tons more difficult. Setting that up by hand would be very problematic. So, you'd really want to use a mocking library there. So, JavaScript you can just get a lot farther a lot easier as long as you understand the language of it.

**CHUCK:&nbsp;** Yeah, well and I think you also illustrated well the reason why mocking makes thing simpler, is because then you don't have to have a fully inflated object with valid state in it for all of the things that I can possibly do. It just has to respond to one message and send one answer back. And so, you just create an object that duck types that one interface and that's it.

**JUSTIN:** Joe mentioned something about how convenient it is to get up and go with JavaScript because you can just go in and have it out and put in some new functionality. And if you guys wouldn't mind, Jamison and I were chatting offline a little bit. I'd like to steal the conversation to just talk about Node.js specifically and the broader culture that we find ourselves in. Because I think that there's actually a real human reason for why I spent the time to write testdouble.js. And I'd like to start with putting Jamison on the spot and asking him if he thinks I've been too negative towards Node.js the last few years.

**JAMISON:&nbsp;** I think you are probably the most negative person that still uses it [laughs] that I see consistently.

**AIMEE:&nbsp;** [Laughs]

**JAMISON:&nbsp;** I don't know that it's too negative, though. I think sometimes people who adopt a technology adopt it because they like it. And then there can be this tendency to feel like you need to support it. Like you have to be on the technology's side and you can't point out what it's bad at, maybe. Or you need to kind of be a cheerleader to make sure it succeeds. And I think it's really valuable sometimes to get an outside, I don't know, not an outsider because you do a ton of Node but I would say you have a perspective from lots of other communities as well where you can look at some of the things in the Node community and say like, “Hey, in community X this specific thing is way better and why can't we make it better in Node?” Was that enough of a waffle, wishy-washy non-answer to avoid getting in trouble? [Laughs]

**JUSTIN:&nbsp;** No. No, that I think certainly helped pretty well just to say everywhere I go, we started this call before recording and somebody said I'm like a Ruby guy. Well, when I go to Ruby conferences I'm a JavaScript guy. When I go to Agile conferences they just don't know who I am.

**JAMISON:&nbsp;** Are you the waterfall guy there? [Laughs]

**JUSTIN:&nbsp;** Yeah, apparently. So, and I think you're right. Because people pick sides. They get invested in their favorite technologies and then it's like they're rooting for their team. There's a lot of good stuff about Node and primarily I think that the conversations that it starts, the way that I look at any technology is through a pop culture kind of lens. Like I don't think of Node as being necessarily a popular technology on its own technical merits per se. I think of it as through the different pressures the industry is under right now. Like the prevalence of nine-week bootcamps everywhere has us looking for ways to help people get started in that short period of time. So you're not going to teach people Haskell in nine weeks to build production apps. With JavaScript it's relatively easy to get started with. All of the different millions of npm modules that can plug anything up to anything else are like catnip for startups that just want to see a proof of concept go to an MVP in 30 days. But what…

**JOE:&nbsp;** Hey, can I break in really quick and just say if there is a nine-week Haskell program, please let me know. I'm interested.

**AIMEE:&nbsp;** Yeah, I want to go, too.

[Laughter]

**JUSTIN:&nbsp;** You now actually, I think a Haskell summer camp would have a pretty big market. I think there are a lot of people who'd be interested in that. But I don't think that they'd be promising 90% of candidates getting as hundred thousand dollar [a year]…

**AIMEE:&nbsp;** [Laughs]

**JUSTIN:** Jobs in nine weeks…

**JOE:&nbsp;** Right.

**JUSTIN:&nbsp;** Programming Haskell.

**CHUCK:&nbsp;** Well, and you'd have to make sure that the business model is functional. Sorry, I couldn't help it.

**JOE:&nbsp;** Ha! Ha!

**JUSTIN:&nbsp;** Ha!

**JOE:&nbsp;** Ha!

**JAMISON:&nbsp;** Hey-oh.

**AIMEE:&nbsp;** [Chuckles]

**JUSTIN:&nbsp;** But Jamison, I think what I've slowly learned, I was taken aside several times and told, “Be more constructive. Provide more solutions. Don't be so negative. And don't just make people feel bad,” which I think is what I…

**JOE:&nbsp;** Don't you just hate people that say that?

[Laughter]

**JUSTIN:&nbsp;** I don't want anyone to feel bad. If somebody loves working with Node, well I want to do… I feel, I think that I started feeling like the oxygen had been sucked out of the room. Everyone's talking about async, small things, get up and go, build something in five minutes, adopt, adopt, adopt, start little tiny stuff and then make a big mess later. And the worry that I had was people wouldn't think about all of these other conversations. Like none of it was really informed by all of the design principles I learned from extreme programming. We don't talk a lot about domain-driven design or object-oriented programming or functional programming and what those lessons could bring to these gigantic, monolithic, Express apps that I see pop up everywhere that reinvent a million wheels.

And I see a ton of low-hanging fruit for helping a lot of Node.js teams out. And that's frankly like half of Test Double's business now is we work with teams building Node.js to try to show them the cool ways to make systems more stable that we learned in other ecosystems. Because it only makes sense that a lot of it would cross-pollinate and apply. So I'm just not, I wanted to get on the record that I'm not here to be totally just a sourpuss when it comes to Node and npm.

**JAMISON:&nbsp;** Duly noted. So, I would say when I look at the JavaScript community compared to other communities, I see a lot of focus on both learning the fundamentals of the language which is really cool. There's a ton of resources to learn ES6 and get really in-depth familiarity with how that works. And then how frameworks work. There are a lot of resources about building apps in Angular or React or Ember or whatever. I feel like I see less resources around design. I guess that gets to what you were saying, Justin. Whereas in communities like Ruby for example there's a lot of books about designing good applications and then like, in Ruby is a little postscript stuck on the end. But it's a lot focused around Ruby is the specific thing we'll look at, the lens we'll use to look at these technical problems, but we're really focused on teaching you how to design and build good applications. Is that…

**AIMEE:&nbsp;** So, that's…

**JAMISON:&nbsp;** Kind of the same thing, something similar you seek? Oh, go ahead, Aimee.

**AIMEE:&nbsp;** Oh, I was just going to say thank you for asking that. Because I definitely feel that, too. That's one thing I really miss about other programming language communities.

**JUSTIN:&nbsp;** Yes. That's exactly what I mean. I think that the people who have experience in other communities, now that Node.js is not going anywhere, and I think web technologies in general have just eaten the world, that means it's a big enough tent now for us to start having conversations that might cut against or balance out some of the maybe excesses of really small things or get stuff out the door and really five minutes to five days kind of mentality that I see in a lot of Node.js developers, if not all.

**JAMISON:&nbsp;** When you say really small things, do you mean the whole tiny modules movement? [Inaudible]

**JUSTIN:&nbsp;** Yeah, yeah, yeah. The tiny modules. The anti-monolith. The anti-framework sentiment. I think that we could stand to balance things out a little that by voicing for instance sometimes what you need is a framework. If you're doing a thing that's been done a thousand times, if you're building a CRUD JSON API, you probably don't need to come up with your own custom set of routing names, you know? There's probably something that could provide that solved problem, a solution for you, that you'd have the benefit of, conventions that could translate to all your other projects instead of just insisting on building everything all over again with a whole bunch of little tiny, tiny modules that are curated person by person. These are conversations that I think happen in the corners. But because they aren't of the ilk that made Node popular, they're seen as being anti the future by a lot of the advocates. And getting back to your point about teams, I feel like they're viewed as being just spoilsports.

**JAMISON:&nbsp;** So, are you saying that these abstractions maybe exist in Node and people just aren't using them? Or just that the Node community itself just doesn't put enough effort on them to build them up?

**JUSTIN:&nbsp;** Right now I'm focused on awareness, right? Like I try to have the hard conversations about design, about testing, lessons that I've learned. I'm thinking about putting together a talk this fall called Agile.js where literally I just go through a deck of, “Here's cool stuff I learned from the Agile community that you probably don't know if you've only spent time with the JavaScript community.” Because the Agile community doesn't write a lot of JavaScript, it seems like.

I'm not here, I'm sure that a lot of… you look at npm right and there's 300,000 modules. I'm sure that a lot of them do exactly what I need but I just don't know about them yet. And I found that scratching my own itch by articulating the thing that I really mean for an opinionated library like I've done with testdouble or with teenytest which is a test runner that we've made, our hope is that we can use those as [concretions] to continue to carry the conversation forward. And hopefully, the community as it matures becomes more and more open to having multiple perspectives on things like what makes for a good test or a good module. And I'm just hoping to see things open up.

**JAMISON:&nbsp;** Hmm. So, let's say I am a JavaScript developer and I come up in this Node world where the value is a lot on features and product and getting them out the door and building stuff. And I do want to get started digging into design and abstractions and things like that. What do I do? Where do I start?

**JUSTIN:&nbsp;** Yeah, that's a great question. I wish I had a book that I could hand you that would have all of the examples in JavaScript. But instead I have a bunch of books with all the examples in Java which is the non-script edition of JavaScript. It's [inaudible].

**JAMISON:** The lite edition if you will.

**JUSTIN:&nbsp;** Yeah. You know, I would go back to some of the classics. A lot of people learned a lot about just the breadth of design thinking out there by looking at Martin Fowler's Refactoring books and Patterns books back in the early 2000s. Some of my personal favorites are 'Domain-Driven Design' which is just identifying a way of getting away from the spaghetti of having a file listing that contains 15 different concerns but instead articulating a world view that tells you how to model and structure your software to map to how humans actually talk about the problems that it's solving, right? That makes it more maintainable because everyone uses that language already. There's I think just a treasure trove of books that are 10 years or older that we could all benefit from. And Chuck knows a lot of them.

**CHUCK:&nbsp;** A lot of the books? You named a lot of the books that I would have recommended. We've done book clubs on a lot of them on this show or on Ruby Rogues.

**JUSTIN:&nbsp;** Unfortunately I don't think I'll ever have it in me to write a book. That's maybe the ultimate thing to be able to say is like, “Here are all my opinions and here's the book to go with it.”

**JAMISON:&nbsp;** And they're on paper. So now…

**JUSTIN:&nbsp;** Yeah.

**JAMISON:&nbsp;** They hold more weight.

**JUSTIN:&nbsp;** Yes. And I'm more important because I am now a published author. I want to have written a book. I just don't have the appetite to write one.

**JAMISON:&nbsp;** Ghost writers sound like the solution for that.

**CHUCK:&nbsp;** [Laughs]

**JAMISON:&nbsp;** Does this just happen as a community matures? Is it just a function of the age? JavaScript has been around a really long time. There have been people doing it for a really long time. But I would consider the JavaScript community of today feels like it just came about through Node and that's not very old. Will it just happen naturally as people in the community mature and the community itself gets older? Or does it…

**JUSTIN:&nbsp;** [Inaudible] Yeah.

**JAMISON:&nbsp;** [Inaudible] a deliberate action.

**JUSTIN:&nbsp;** Yeah, this gets at one of my favorite phenomenon in the social side of how language ecosystems rise and fall. I got into Java when I was first learning to program in the late 90s. And you could just see this Cambrian explosion of stuff getting created as people realize they could publish a JAR to a personal website. People could download the JAR. You start to see tooling like Maven come along that make it easier and easier to suck in additional JARs for dependencies in Java. And Ruby was the same thing. The first couple of years, everything needed to be invented all over again, right? Like if you needed a thing that made an HTTP request in a nice API somebody had to be the guy who made that. And so, it's a great way to get in the ground floor and publish stuff and create a lot of very core, important tools. And Node's had that phase, right? We're past that.

The next phase is a stabilization. People start to build higher-order stuff like frameworks. People start to ask questions about well, I've got this legacy three-year-old app now and it's a mess. How do I rein that in? You know, I think that the interest in Node.js about testing has increased. When you start to get into phases beyond that, you start to look at what does enterprise adoption look like? What are their concerns that they want to make sure are taken care of if they're to adopt it or if they're to maintain it? And as things start to settle down it's inevitable that you'll have a lot of the big names who are mostly, they're excited about new, shiny stuff, they'll start to leave. And naturally you'll have a lot of attrition because a lot of the problems are just solved now. I think we're going to see that in Node.

I don't know if we'll ever see that when it comes to web technologies at large because everything is constantly evolving and there's just so much behind it. But I think you're already starting to see Node stabilize to some degree just because people like me are starting to come to the table and talk about it.

**JOE:&nbsp;** So, I read this article and I really, really enjoyed it and I liked your analysis of, “Hey, this is a problem. Here's how testdouble handles it.” And there are a few points that really stuck out at me. In fact, one thing that's interesting is you said, created these convenience functions and let me know, as far as I understand, Sinon doesn't have these. Let me know if I'm wrong. And I was looking and I'm like, “I'm pretty sure Sinon can do that.” I went and looked and yeah, I think we can do that. I say this and then you responded with this very well thought out, very intelligent, obviously something you've really done a lot before saying, “It's actually not the same thing because of this, this, this, and this.” So, I can tell right off the bat that you really understand the problem domain very well. But again like I was saying, it's pretty impressive that what you're looking for is a solution that is opinionated and leads you to the right space.

So, a couple of things that testdouble does that I really like as an improvement over Sinon is one thing that you mentioned. It focuses on a specific task or set of tasks related to testing. And rather than Sinon which tries to be everything to everybody it's got its opinions and it says, “Do things this way and do them right and they're easy and straightforward to do.” And I like that. I was not a big fan of Sinon's mocks. Sinon has both spies, stubs, and mocks. And I think pretty much stubs is a superset of spies. So, I would always use stubs. And mocks act differently than stubs. And I didn't like the way that they worked. And you actually talked about this in your article, that mocks in Sinon violate the AAA rule.

And so for those that don't know what the AAA rule is, that's the Arrange, Act, Assert. And so, this is just generic advice when you're writing tests. A test should be in three phases, right? You should arrange it and set everything up. And you should take one action and change the state somehow. And then you should assert or check that what happened is indeed what you expect it to happen. And it's been discovered over a long time when you violate that you start making tests that are less easy to maintain. And so, the way that mocks work in Sinon is that they screw up the order. You have to assert first and then you can act afterwards. And so, I really like how testdouble allows you to do the same thing that mocking does but allows you to assert last. So, for me that was a big thing. Was it hard for you to find a way to make that whole thing work or was that pretty straightforward for you that, “Oh, I want it to be like this and this is how I can do it”?

**JUSTIN:&nbsp;** The implementation for the library is pretty simple I think. And the best way to explain it is to say to anyone listening who's made it this far who's never used a mocking library before and is probably somewhat confused, if you have a fake function there's really two things that you want to be able to do with it, for the purpose of writing a test. One, you want to make it return stuff given a set of arguments. So, if I have a fake function called bark and I want it to return woof, I need to be able to configure that somehow. And the way that you do it in testdouble is you say 'td.when' and then inside the parentheses you just call the thing like you want it to be called by the thing, by your subject that's under test. And then say, then return woof. To verify it I tried to make it as simple as possible by just making it completely symmetrical. You say 'td.verify' and you can verify that interaction took place. And that's really only appropriate if the thing that you're testing has a side-effect. And so, you can't tell by return value that it did its job. And that's it.

It's just this real simple data structure essentially of keep track of what all the test doubles are. Every time somebody stubs something, throw that in an object and remember it for later. And then every time somebody invokes it, go look through all of the stubbings in reverse order and be like, “Okay, the first one that applies, like maybe it was passed with the argument one, that matches the stubbing configuration. Return that thing.” Or call back that thing or return this promise, depending on how you've configured it. And so, what I found is that if you have an opinionated API that's definitely narrow, it makes the implementation easier because you don't have to think of so many edge cases. And because this is such a simple transactional way of looking at mocking, it's really not that complex of a library.

**JOE:&nbsp;** Yeah, so I was pretty impressed that you managed to figure that and make this library handle that the whole, verify these interactions and do it in a simple way and still maintain the Arrange, Act, Assert setup that you want to see out of tests. And whenever you can't see that, it's very frustrating. And one of the big reasons why with Sinon I never used mocks was because it violated the Arrange, Act, Assert. That and it was just kind of a more unwieldy API.

I also really like this. I think you made a good choice with the whole recording API. Like you call it, you actually call what you want it to do and tell it, “When this happens, return this,” so you're kind of recording what you want it to happen. And then you make it go and if it happens according to plan, then everything works out and if not either errors are thrown or you get that whole, “Hey, you didn't call this method with the right functions or right parameters.” So…

**JUSTIN:&nbsp;** Yeah, if anyone goes and checks out testdouble's readme the first thing you'll see is that the API is kind of goofy. It's unlike a lot of JavaScript APIs out there because you're actually, you configure the thing by calling it exactly like you want to see it. And it works that way by very simple implementation that's not black magic even though it might feel that way because it's so different. But the reason I did it was I didn't want to have to introduce in the API to describe how a function gets invoked. Because we already have that. It's called a programming language and that's what they're all about, isn't it?

**JAMISON:&nbsp;** [Laughs]

**JUSTIN:&nbsp;** So, just invoke the function how you want to see it. And that way, you can easily grep from your tests into your source code. You can copy and paste from the test into the production code if you need to. Save a step. It makes everything a lot easier to find instead of having some poor man's attempt at imitating what it looks like to call a function by configuration, like by having a chainable API. You just call it, right?

**JOE:&nbsp;** That was awesome. Another thing I'm super impressed with is your error messages. Again, I haven't used it so I haven't gotten to the place where it's like, “Oh, you promised these error messages but you didn't deliver. In this case I'm getting a totally unusable error message,” but at least according to the documentation the error messages that you're putting out is really, that testdouble puts out is really impressive because it's very readable. It says, this is an example, I'm going to read from the documentation for people that are just listening. If you verify that what you wanted was that the method was called with a parameter of Jane for example, and what happens is it was called with a parameter of Joe, a string, right? So, the error message says, “Error. Unsatisfied verification. Wanted called with Jane but was actually called with Joe.” It just reads exactly what your problem is and gets you right to it.

And you point out that in Sinon or in something you hand-roll you might at best get, “Hey, true is false,” or at worse just get something else completely unintelligible. And it's so frustrating to work with libraries or technologies where you have to begin memorizing, “Oh, this error message, what this really means is this thing.” And you begin memorizing what different error messages or different exception types actually mean and the likely culprits that they are. But when the error message actually points you right at the problem, that's so great. One of the reasons I love Elm for example is it's really good at doing that. So, I was really impressed with [inaudible]…

**JUSTIN:&nbsp;** You know, Chuck…

**JOE:&nbsp;** Effort you put into it.

**JUSTIN:&nbsp;** Right on, man. Yeah. Chuck mentioned earlier, Jim Weirich was one of the first people he sat down with and wrote some tests that used mocks in them. And one thing that Jim impressed upon me when I was writing [inaudible] which is a spy-style test double library for Ruby a few years ago, he sat me down and he was like the most important thing in any testing library are the messages. Because the messages should be able to tell the person everything they need to either fix the test or if they're practicing TDD take the next action without having to go and print something out or debug something or take some unrelated step. Because that all breaks flow. And so, making sure that all of the testing tools that I write have really, really great messages as well as an ability like in testdouble a lot of people get confused about mocks. You can always pass any mock to 'td.explain' and it will tell you what the current state of it is, how it's been configured, and how it's been verified. Just to give you a heads up of this is what you're currently looking at instead of waiting for something to blow up.

**JOE:&nbsp;** Right, yeah. That was another really cool feature is that whole explain function that tells you exactly what happened to it. Which when you are practicing test-driven development what you want is to get into a very simple and straightforward flow of, I make a small change to a test and now it's broken. And then I make a small change to my code and it goes, it starts passing again. And I'm slowly working myself, and I never get to a point where I have to spend an hour or a half an hour digging into some weird issue. Even five minutes is too long, digging into some weird issue like, “This isn't working. How do I make this work?” You want to avoid that as much as possible. And mocking libraries are often the place where this can happen where if you have something set up and all you just get is a failure, it just says, “Nope, didn't work,” and you don't know why because you're having a hard time seeing under the covers. And these messages, letting it know, “Hey, you called it with this parameter then you called it with these parameters and then you called this other function with these parameters,” gives you perfect introspection into what's going on in your code. And I really like that feature as well.

**JUSTIN:&nbsp;** Awesome, man. Thanks. I really appreciate it. I'm really unusual in that I very much like compliments.

[Laughter]

**CHUCK:&nbsp;** Alright. Well, I've got 15 minutes…

**JAMISON:&nbsp;** We'll keep [inaudible].

**CHUCK:&nbsp;** Until the next podcast. So, we need to get to picks. Jamison, do you want to start us off with picks?

**JAMISON:&nbsp;** Yes. My first pick is unemployment. I got [inaudible].

**AIMEE:&nbsp;** No! So sad. [Chuckles]

**JAMISON:&nbsp;** I know.

**AIMEE:&nbsp;** But happy.

**JAMISON:&nbsp;** We parted amicably. I like Kuali. It's a great place to work if you're looking but I'm going to be taking a month or so at least to do nothing and just be a dad and do React Rally stuff. So, I'm looking forward to that. I've never really done that in my life.

Which leads into my second pick, React Rally. React Rally is a conference that Matt Zabriskie and I are putting on in Salt Lake City, August 25<sup>th</sup> and 26<sup>th</sup>. We're just finalizing preparations for right now and we're really excited about how it's shaping up. It's focused on React. Hopefully you got that from the name. But really excited about the speakers we have, the events that we have, the theme and the setup of the conference. I think it should be a really good time for attendees and speakers and everybody. So, check that out.

My last pick is not self-serving [chuckles] for a change. It's just a tweet by Julia Evans where she talks about how to be a wizard programmer. I really, really, really like her thoughts on programming and development. And this one, she talks about how important the skill of asking questions and being around people who can help answer your questions is. But then after that eventually if you keep doing that, you'll get to questions that other people can't answer. And that's where you have to figure out the answer. And you might be the first person ever to ask that question and figure out the answer. And that's what makes someone a great developer.

So, those are my picks.

**CHUCK:&nbsp;** Awesome. Aimee, what are your picks?

**AIMEE:&nbsp;** Okay. So, I actually don't have any technical picks this week because as we were talking about at the beginning of the show I've been going through a lot of just personal things that will in time probably come out. So, it's been a really, really rough couple or three weeks for me. And so, my pick this week is probably going to be to take a step back and as you look around and you're just going through your day-to-day, one thing that the pastor did a sermon once that I really, really liked is if you're on the road and somebody cuts you off and you get angry with them just maybe take a deep breath and try to think. You don't know necessarily what that person is going through. Maybe they're rushing to the emergency room because someone in the back of the car is really sick. Or who knows? But I guess that's my pick this week is to just kind of try to see the good in people. So, that's it. [Chuckles]

**CHUCK:&nbsp;** Awesome. Joe, what are your picks?

**JOE:&nbsp;** So, this is going to sound kind of funny but my first pick is going to be Sinon.JS.

**JAMISON:&nbsp;** How rude. Depending on what your second pick is.

[Laughter]

**JOE:&nbsp;** Oh guys. Thanks for putting under some pressure. No, we've been talking a lot about some of the problems of the Sinon API and how testdouble.js seeks to solve those with a slightly more opinionated and focused framework, which I really like. But I think one thing that could be missed in all of this is the fact that Sinon solves a problem well and is a great tool. Maybe it's the day of testdouble has arrived and it will slowly become the de facto mocking library. But that doesn't take away what Christian Johansen did with Sinon. And so, I want to pay my respect to that. We had him on the show long ago, many years ago. And I was really excited to talk to him because I use Sinon a ton and was really impressed with the work that he did and the pioneering that he did to make a really good mocking framework. So, I want to pick Sinon as a show of respect and just all the difficult work that he did to give us something that really worked. And so, that's going to be my pick.

**CHUCK:&nbsp;** Alright. I've got some picks here, mostly not technical picks. I've got a whole bunch of stuff going on this week. I'm going to be out next week because I'm going up to Wood Badge which is Boy Scout leader training. But this last week I read a book, or listened to a book on Audible. It's by Zig Ziglar and it's 'How to Stay Motivated'. And it's kind of funny. I just feel like I have better ideas about how to do better with life. It's not any one grand idea that makes things better but just a whole bunch of principles that you can apply in your life that help things get better.

So, I've actually set the goal to listen to everything that Audible has from Zig Ziglar that's in English, because they have Spanish programs and stuff on there too. I'm not a fluent Spanish speaker. I get better with Spanish as it gets closer to Italian. We'll put it that way. But anyway, super great books. I'm currently reading 'Over the Top' and 'See You at the Top' which are two of his other books. They're not very long. The audio programs on Audible are terrific because he's actually speaking. He's not just reading the book. And they are terrific. I know Zig died a few years ago but what he's teaching there I think are sort of timeless principles for people to be successful in life. So, if you're looking for something like that, then definitely check it out.

And then the other pick I have, I read these books quite a long time ago. I think most people have at least heard of them. But I've been rereading or re-listening to the Harry Potter books. And it's just a really nice way to relax. So, I'll just put that out there.

Justin, what are your picks?

**JUSTIN:&nbsp;** Today my first pick is going to be an [OS] distribution for Raspberry Pi called RetroPie that kind of comes out of the box. It lets you throw a bunch of NES Nintendo game into its emulators and you plug it into a TV and then you've got a deck of card sized retro game console. It solves a real problem for me which is I travel three quarters of the year the last couple of years and I [inaudible] each night. And so, I get really, probably the thing I hate most about traveling [inaudible] a rhythm of gaming. So, I think I'll be able to travel with it. Now the downside is it's in this clear Plexiglas box. And there's memory chips and stuff poking out. So, I'm sure that the TSA is going to confiscate it before [inaudible]. But at least as long as it lasts, I'm excited to have it.

The second pick is a talk that I saw in Norway [last month]. It's 'How Elm Can Make You a Better JavaScript Developer' by one Jamison Dance and somewhat recently. So, if that hasn't been a pick on the show yet before, I'd strongly recommend it. I see dozens of talks every year and this one made me sit up straight because I learned something and it was entertaining. I thought it was really good. So, whoever Jamison is, that was a good talk.

And then on the topic of conferences again, I'm actually going to be in Nebraska for the very first time in my life at the end of August to keynote NEJS, a Nebraska JavaScript conference over in Omaha. And it's a single-track, single-day conference. It looks like it's going to be a lot of fun. So, if you're in the area, I hope you can check it out.

**CHUCK:&nbsp;** Alright. If people want to follow up with you, get to know you better, they want to get hired by Test Double, or they want to hire Test Double, what do they do?

**JUSTIN:&nbsp;** Easiest thing to do is to just email us. You can say hello@testdouble.com and say hi and we'll find the time to have a chat. You can find us obviously at TestDouble.com or there on Twitter. If talking to a corporation is too scary, I'm Searls on Twitter. And I've got open DMs and I'm always happy to talk to anyone about anything. Even if you're just looking for some free tech support or free advice.

**CHUCK:&nbsp;** Alright. Well, I know that the internet tends to misspell stuff, so how do you spell Searls?

**JUSTIN:&nbsp;** Searls, so my wife's a teacher and she teaches her kids every year on day one that you spell Searls or pronounce it like the word pearls but with an S instead of a P. So, it's S-E-A-R-L-S.

**CHUCK:&nbsp;** Alright. We'll have that in the show notes, too. But I know some people just listen to the show and then they might tap it in on their phone. So, alright. Well, we'll go ahead and wrap this up. Thanks for coming and we'll catch everyone next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**
