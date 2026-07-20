---
Title: Founder of Paperclip shows how (companies.sh launch-day interview & screen-share demo)
Author/Speaker: Paperclip founder (anonymous, cartoon avatar; states he comes from "the crypto world") interviewed by host "Andrew"; presented by Zapier
Date: Unknown — recorded on companies.sh launch day; Paperclip stated to be "3 weeks old" at recording
Duration: ~20:49 (from final transcript timestamp)
Topics: Paperclip origin & value proposition; persistent agent instructions; skills & skills.sh; companies.sh one-command company installs; G Stack (Garry Tan); Remotion video demo; hiring agents with skills; PARA memory skill; routines (bookmark strategy report); Tailscale mobile access; OpenRouter free/experimental inference; company export & marketplace ideas; OpenClaw comparison
Confidence: Medium — auto-generated (NoteGPT) transcript; product names and commands occasionally garbled (e.g., "NPX paper clip AI onboard"); creator is inherently promotional
Reviewed: No — pending human review (15 min max)
Status: Raw source; analyzed in reports/paperclip/PAPERCLIP_COMPREHENSIVE_SOURCE_REPORT_2026-07-20.md
---

# Raw Transcript (verbatim, auto-generated)

00:00:00 - 00:00:53
I created Paperclip to enable people to run a zero human business. Andrew, look at this. We've one shot an entire company. We just released companies.sh, which is like the app store for agentic companies. I don't want to oversell it. I just want to show what's possible today. Okay, let's do a screen share. I'll show you how to use Paperclip. Presented by Zapier, the AI automation company. You want to show me your company first? Sure. This would be the company that I use for running Paperclip itself. It's

00:00:27 - 00:01:23
actually pretty small right now. We've got the CEO, we've got the CTO, which has a lot of the like coders under it. So, for example, >> of these are agents. The CTO is an agent. The coder is an agent, etc. Yeah, that's right. And my my main coder that I use would be either Claude or Codex. You know, I think if you ask any person that uses AI agents day to day, they can tell you that they all have really different personalities and different strengths and weaknesses. >> Okay, but before we before we continue,

00:00:55 - 00:01:41
because you're going to go deeper and show me how this works, I got to ask you, why am I looking at a cartoon and not a human being? Yeah. Yeah, so um I come from the crypto world and like I don't mind having my anonymity and that's just something I like to carry through. All right, I'm the opposite. I want as much attention as possible, but let's continue. So, I see this you were saying about all these different developers. This I So far all I'm looking at is an org chart.

00:01:18 - 00:02:21
This is not the special part. Show me the special part of Paperclip. One of the reasons that I created Paperclip was because I was trying to build companies in the terminal using Claude code and cursor and I had way way too many things going on and I would come back and I wasn't able to remember what anybody was doing or what anyone was working on. So, with Paperclip, what you're actually able to do is keep everything managed like you would with a task manager and all the conversations are tracked, all of the

00:01:49 - 00:02:41
costs are tracked, and everything that your agents do, you can go back and see how they did it, if they did a good job, if something went wrong, how to fix it. Something else that you can do with Paperclip is it helps you manage your agents' instructions. If you're working with AI agents, that's one of the main things that you need to know is that your agents wake up every time you hit them, they wake up and they're insanely capable, but they have no idea who they are or what they're supposed to be

00:02:16 - 00:03:14
working on or what they worked on yesterday. Paperclip makes that easy because, you know, I can have my UX designer have a certain sort of instructions on how it's supposed to work. I can have my video writer have instructions on how it's supposed to work. And then, you can also configure skills. So, I don't know if you've seen skills.sh, which is a website that a lot of people use for managing their agent skills. Have you used this? No, I haven't. Yeah, so this is from the guys at Vercel

00:02:45 - 00:03:56
and it's basically a way that you can teach your agents different types of abilities. So, for example, web design best practices, how to make videos with Remotion, how to generate AI images. So, this is a really powerful way that if you're using Claude code or Codex or any kind of coding agent to do your to run your business, you really want to look at different skills that other people have created because it gives your agent superpowers. So, for example, this morning, we released a a new website companies.sh, which gives

00:03:20 - 00:04:35
you one command installs of entire companies and we'll talk about this. Mhm. Um but one of the things that I needed was I actually needed a video for it. And so, I asked my AI agent to create a video. I asked my CEO, I said, "Hey, um I created a new issue." I said, "Um can you hire a video writer and give him the Remotion skill?" So, this was something that I did earlier this morning. And the agent was hired. And I can look here and I can see, "Yeah, write the script for a 60-second

00:03:57 - 00:05:04
video about the companies.sh launch." So, I asked it to write a plan and it wrote this plan, which is here's what the audience will take away, the messaging hierarchy, shot by shot of what the video should be. Um and then, it used this Remotion skill, which I downloaded from here, to actually create the video for me. What it was able to do was it was able to take um the the brand guide that I had already set up for Paperclip, as well as a few of the basic ideas that I had for how we were going to pitch this company's

00:04:31 - 00:05:23
video. Instead of launching this tweet with just text, I actually had this interactive animated video for the launch. >> But now, at what point did you give it the skill? When I hired the agent, I simply told the CEO to give him that skill. Oh, I see. So, you got the skill and then you sent it over, you sent the link over to the skill and you said, "Hey, CEO, create somebody who's going to make a video for me. Use this skill. Boom. That's it." Exactly. That's all you have to do. So, you could come here

00:04:57 - 00:06:04
and say, um you know, let's say I want someone who can make Excel spreadsheets, for example. I could copy this in here and I could go to my CEO and say, "We need a like data analyst who has data skills for Excel." Um and I would assign this to our CEO and we'll say, "I give him this skill." So, we'll let that run in the background. Maybe we can come back to it a bit later. >> And then, okay, and that's how you end up having another agent who comes in with skills. What are we looking at

00:05:31 - 00:06:30
here? These are all the skills? Yeah, so these would be the skills that you have built into your organization. So, we have a humanizer skill, which is used for helping your AI write a little bit better. We also have a memory skill here, which is the Tiago Forte's PARA method of memory. >> Mhm. Um this skill is actually from Nat Eliason, who I know that you've spoken with before. And this gives your agents memory over a long period of time. So, And these skills right here are skills

00:06:00 - 00:06:59
that are universal to everyone who's working or every agent that's working for me. Um so, you can choose because one of the downsides of models of today is that if you load too many skills in, they start to lose track and your performance degrades. You really only want to enable the skills for the agents that are actually going to use them. All right, I'm I'm getting this. Project management built for agents with skills and memory features that agents are going to need. Let's take a look at

00:06:30 - 00:07:33
what you created and what you launched, which is now basically an app store where instead of adding apps to my life, I'm now adding companies. And these are the different types of companies that I can have. Walk me through what what's in here so far and obviously we're recording this on launch day, so there's not that much. Um one of the things that I have noticed and I'm sure you guys have too is that there are so many new links or repos shared every day on different ways that you can make your

00:07:01 - 00:08:04
agents better. So, for example, a really popular popular one is this one G stack by Garry Tan of Y Combinator, where he provides a set of skills. He's the president CEO of Y Combinator. He has skills in here that um let you have a office hours like you're in NYC and they're quizzing you for like if you need help or if you're trying to build your business. They have how to do planning, how to plan engineering, design consultations, all these things, right? So, >> Essentially, he's taken all the

00:07:33 - 00:08:22
different things that they bring to Y Combinator founders who are part of the accelerator and he's turned them into skills here that you can invoke if you're in Claude code. I I've used them. It's actually helpful. All right, and what you did was you say, "Well, if he's got all of these, he's essentially creating a company where agents can take on these different roles, I'm now going to make it into a one-click, one-shot company creation based on his model."

00:07:57 - 00:09:13
That's exactly right. So, when you install um G stack into your Paperclip instance, you will get um the agents with all of their skills installed. So, now you can start to use G stack um from Paperclip with in a way that's very very easy. So, he recommends, for example, having a QA engineer look at the work that you've that that was created. And so, you've added that role right there. That's right. And one of the things that I am finding is that um there are a lot of patterns when using agents that are

00:08:35 - 00:09:32
not really clear. But in reality, a lot of the best companies have relatively sophisticated patterns of agents checking each other's work, agents giving work back to one another, but there really has been no place where you can actually share those patterns with other people. And so, that's what we tried to build here. Um even though, you'll notice this isn't a Paperclip domain. So, the reason is is because this is a standard that we hope for other companies to use to make shareable

00:09:04 - 00:10:17
companies. Okay. >> And the idea is as people learn these patterns to make their agents more effective, we'll all be sharing them with each other and all benefit as a result. Okay. Can I see one of these companies working and then we'll launch one right now together? Yeah, absolutely. So, here for example would be the Don Cheetos game studio, which is quite large and so, you can see here they've got creative directors, narrative directors, art directors. And let's see here. So,

00:09:41 - 00:10:41
um I >> active Paperclip experience right here, right? Um it yes. So, I would say this that like one of the things Paperclip is 3 weeks old today. And I would say that one of the things that we're still working on is making sure that Paperclip keeps your agents working when you want them to work. Uh there's a feature we're working on that's not out yet called maximizer mode and it will ensure that your agents never stop working. So, um here what we've done here is we we

00:10:10 - 00:11:19
created a first game where we said, you know, we're making a bullet hell game in uh this game engine called Godot. Um we can come here and we could, you know, we could basically ask the CEO like, um follow up on all the work and like keep people moving. You [laughter] probably couldn't have to do this, but uh >> Okay. you know, yeah, there we go. So, starting with um this issue. Um what the CEO will essentially be able to do is come through here and make sure that these things have actually

00:10:46 - 00:11:43
succeeded, right? So, we've got a project set up in Godot, a folder structure for players, enemies, weapons, things like that. Okay. >> Um we could also come over to the G stack if you wanted to So, this is a company you created using Garry Tan's G stack. This is this is what you showed me the template of and maybe we can create this together now. Okay. >> Sure, yeah. Absolutely, yeah. By the way, one big question that came up when I showed how Catherine had set this up is do you have to use Claude's models for

00:11:14 - 00:12:14
this? You actually do not have to use Claude's models for this. Wait, just describe what you just did right here. You just you're doing what here? Oh, yes. Okay, so I have switched to um a terminal. >> Terminal. Yep, of course. The terminal app on my Mac. And if you want to install paper clip itself uh for the first time, you can call uh paper clip AI onboarding. So, NPX paper clip AI onboard and that will walk you through the onboarding. >> And I need to do this before I install

00:11:44 - 00:12:47
one of the companies, one of the company >> to, actually. Uh the good news is is that it will actually um install paper clip for you. So, all we need to do here is we can go to the website and copy the command. Uh did that off screen. We'll paste it in. NPX NPX is is a tool that most Macs have installed. Mhm. Um companies.sh add uh paper clip AI companies G stack and this will run for a minute. And it'll say, "What service do you want to import your company to?" And there we

00:12:16 - 00:13:17
go. We'll get that imported into It gives us a bit of a listing here of saying, "All right, how many agents are you going to get? How many skills are you going to get?" And just confirm that we want to import it. All right, so we can switch back over to this new company. Um something else with the models is there's a tool called open code that uses um this website open router and they have a um a leaderboard of models that people use there. Um And some of these models This is a place

00:12:47 - 00:13:49
where This is a place where a AI model companies test out their new models before they release them to the public. So, sometimes Grok will have their model here under an anonymous name. Um and and they often have free models. So, for example, here you can see there's step 3.5 flash free. There were a couple other models last week that were very very high quality. So, you can actually send your agents um here and get essentially free inference. All right, what about uh the web experience? Can I actually access the project

00:13:18 - 00:14:24
management experience somewhere else? Yes. So, um we will be creating a paper clip cloud-hosted version, but for now what you can do is there is a tool that a lot of people use called Tailscale. And uh Tailscale has a free plan. It's actually very very handy because you are able to connect your phone to your computer through the internet. So, what I do is I run paper clip on my laptop and then I run Tailscale on my laptop and my phone. >> And so, when I'm at uh you know, when I'm out and about, the the paper clip

00:13:50 - 00:15:01
has a mobile version and it works quite well. I use it all the time. Okay, let's stick with what you were doing before, which was now you were installing Garry Tan's uh company. Is it is it set up? It is. This is what we just created. >> That was fast. >> just It's amazing. So, you know, do we have a business idea that we want to ask Garry Tan his advice on? So, like >> use office hours and ask um advice for our new business idea, which is Um here's here's a new business idea.

00:14:26 - 00:15:31
Install paper clip uh for people. I've been noticing that open claw has got this biz this uh economy of people who are installing open claw for first-timers. I think with all of these technologies, there's there people who are watching it, who don't want to do it themselves, who want some customization. Let's see what what happens when we do this. Now, the thing that when I've used this skill in the past, the thing that I like about it is how fast I go go back and forth with uh

00:14:58 - 00:16:01
with Opus to ask questions and answer its questions and so on. Here, by creating a ticket, aren't I just slowing it down? I would say that um if you simply wanted to kind of chat with uh the office hours skill and you wanted the fastest response time, you can still use Claude for that um directly. But, if you find that you are trying to manage 50 different things with your agents and you can't remember what every tab is doing and you don't know what they're doing, then that's

00:15:30 - 00:16:34
where paper clip really shines for you. Um So, we'll we'll wait for this to go. Maybe we can look back over here and see, ah yes, so we did hire this data analyst agent from earlier. We can approve it from the CEO. We can see here that our uh data analyst is now part of our team. So, he's got the XLS uh X skill where he could work with Google Sheets and make data for us. Okay. All right, and coming back to this company that we just created, um essentially now I can just keep giving it tasks and understand that the

00:16:02 - 00:17:18
different agents will work with each other based on uh the G stack methodology. That's right. Um so, while we're waiting for uh the office hours to come back and give us some advice, um one of the things that we could do is we could hop back over to um paper clip and I could show you routines. So, routines is where you have work that needs to happen on a recurring basis. So, for example, I use my Twitter bookmarks all the time to store ideas for things that I think will make paper clip better.

00:16:39 - 00:17:45
Um so, for example, I wrote this routine that says, "Hey, I want you to pull my bookmarks and write up strategy for paper clip." I have a strategic ops guy. And I say, you know, this is my plan. Book like sync the bookmarks and here are the guidelines for how I expect you to like make this plan. Then, what I'm able to do is um every morning I come in here and I can see that uh here's my bookmark strategy report. It'll say, "Okay, there's um this tweet that you bookmarked around

00:17:13 - 00:18:07
Anthropic had a tweet for new heartbeat pattern. You should look into that." Or here's a way to track um it's called telemetry, which is like the way to like track what agents are working or what's not. Um and and so on. And so, what actually happens is when I show up every morning, my agents have actually started to do some legwork from things that I was thinking about yesterday. So, I can actually come in here and say, "Hey, why don't you work out like building that as

00:17:41 - 00:18:40
a feature?" And I'm able to sort of like have my agents work for me while I'm asleep. Ah, yeah. So, all right, office hours complete. Oh, okay, so here we go. Here's our office hours for this new business idea. Install paper clip for people. Forcing questions, demand reality. Who's paying for this today? Is there demand for installation or is it just a friction? What happens without you? And so on, right? Like we can walk through this. And kind of yeah, here's the hard truth,

00:18:12 - 00:19:10
services don't scale. So, yeah, there we go. These are some first recommendations from uh Garry about our paper clip install business. >> Essentially, he's saying this is not a good business idea. Yeah, yeah. >> [laughter] >> Hey, easier to find out now. Fair yeah, fair enough. Okay. I'm getting this the vision that you have for this now is that as new methodologies for running a company come up online, people will have a place where they can share them and others will have a place where they could go

00:18:41 - 00:19:35
and install this whole business, one-click install, and the whole company will start to run and paper clip will be what's keeping them all organized. That's exactly it. Okay. >> After you've created a company that you think is good, that you think other people would want to use, um you know, this is the company that you use for paper clip itself, you can come here and click export company and it will export the company in the format that uh that you can use to now share Let's

00:19:08 - 00:20:06
see if I can make this window a bit bigger. There we go. So, it creates an a company export for you um with a read me and diagram and all these things and you can now submit that to your on GitHub or submit it to us and uh it's all packaged up nicely. Why don't you make it into a marketplace where I can sell these company structures? That's a great idea. Well, I think we're going to. We'll probably make a you know, claw hub. Nate Eliason already has a claw mart uh where you can buy and

00:19:37 - 00:20:24
sell individual agents. Maybe we just create something like, you know, like clip mart or something that that that that we can use it or you know, maybe we team up with him. I don't know, I'd have to ask him. I love where you're going with this. All the agents in one, easy to install, easy to get started. In many ways I find that this is much easier than using using OpenClaw and then creating sub agents there and managing them and so on. It's just all in one right here. And of course, for anyone who's using

00:20:00 - 00:20:49
OpenClaw, they can bring their OpenClaw into Paperclip. All right. >> Yep, absolutely. And I love OpenClaw. It's a great piece of software, but I created Paperclip because my OpenClaw just sort of started to fall apart and I couldn't understand what it was doing or what it was remembering or forgetting. And so, yeah, Paperclip is designed to be more human-friendly. All of us start off by creating some kind of project management. Now, it's all here. Bye, everyone.

---

## Actionable Takeaways

### High Priority
- Paperclip's core value is durable oversight of many agent sessions: tracked conversations, tracked costs, retrospective inspection [01:18–02:21]. Verify against the live product before relying on it.
- Persistent per-agent instructions address agent amnesia ("no idea who they are… or what they worked on yesterday") [01:49–02:41]. This maps directly to QSL hiring packets / role charters.
- Attach skills at hire time, and only to agents that need them: too many loaded skills degrade model performance [04:31–05:23] [06:00–06:59].

### Medium Priority
- Routines enable scheduled recurring work (e.g., nightly bookmark-analysis strategy report reviewed each morning) [16:02–17:45]. Useful pattern; needs stopping/notification conditions.
- companies.sh: one-command install of whole companies (agents + skills); founder wants it to become a cross-platform standard, not Paperclip-only [07:57–09:13].
- Export produces a shareable package with README and diagrams for GitHub submission [18:41–19:35].

### Low Priority
- Tailscale (free tier) gives remote/mobile access to a self-hosted instance [13:18–14:24].
- OpenRouter sometimes hosts anonymous/experimental models with free inference [12:16–13:17]. Treat as unverified cost claim.

### Questions to Verify
- Exact onboarding command and package name (transcript renders it approximately as "NPX paper clip AI onboard") [11:14–12:14].
- companies.sh command syntax, repository location, and whether the "open standard" claim is real [11:44–12:47].
- Status of "maximizer mode" (announced, not released at recording) [09:04–10:17].
- Status/timeline of the promised cloud-hosted Paperclip version [13:18–14:24].

### Potential Revenue Ideas
- Installation/customization services exist as a market pattern (OpenClaw installer economy) [14:26–15:31] — but the demoed office-hours skill pushed back: "services don't scale" [17:13–18:07]. Package as productized services, not hourly installs.
- Governed company templates (curated skills + approval-gated hiring) as sellable exports.

### Potential Doctrine Updates
- Third-party skills and company templates are a supply-chain risk → require provenance review before installation.
- "Agents checking each other's work" is presented as a best-practice pattern [07:57–09:13] → adopt, but with accountable human final review.

### Potential Paperclip Improvements
- Explicit task disposition (evidence → review → approve/return) rather than informal completion.
- Built-in stopping conditions when no authorized work remains (counterpoint to "maximizer mode" [09:04–10:17]).