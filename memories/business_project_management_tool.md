```
id: 070e0f90-d129-4079-b74e-8e8e17e43982
title: Project Management Tool
links:
  - 9a9a2fb6-41b7-11ea-b332-7f561162cd24
  - 0522c702-3b6f-11ea-80f9-a36b07e332d7
  - a9054dd6-3b6f-11ea-9c73-93b4117331ff
  - e94746f6-3b6f-11ea-a29f-336b2dc2999d
```

# PMT

When Atlassian [announced][1], that they will stop selling on premise software, I thought about the impact.
A lot of companies are using jira and confluence, 
and there are a lot of alternatives out there.

But what are the core features of the Atlassian stack?

* an issue tracker
* an agile tool
* a wiki like documentation tool?

I thought about starting from scratch, to try out some ideas.

# Features

* LDAP integration
* Issue Tracker
* Time tracking
* Git Integration
* Agile
  * Grooming
  * Sprint Planing
  * Retro
  * Version planning 
* Communication
  * Chat
  * Voice
  * Video (multiple sources at the same time)
    * WebCam
    * ScreenSharing
  * Messaging
  * Group Chats
  * Recorded sessions
* Project Management
* Calendar
* Container Registry
* Build Server (CI/CD)
* Test Management
* Workflows
* Plugins
  * [PlantUML][22]
  * [GraphViz][23]
  * [DrawIO][24]
  * Roadmap Tool
  * [GitLab][25]
  * [Jenkins][26]

# Thoughts

In the last years the phrase `mobile first` comes handy for every kind of new software products. 
Due to the covid pandemie, the next generation of software should be `remote first`.

## remote first

People, who are not sitting in the same room are working seamlessly together.
There is no difference to working on site anymore.
Sentences like `Can you hear me?` or `Can you see my screen?` belongs to the past.

## Matrix

When it comes to collaboration, [matrix][20] can be used for secure, decentrialized communication.
You can use [element][21] as a client, or integrate a client into the whole solution.
During the covid pandemic the university of Innsbruck [introduced matrix][19] as a first class citizen regarding realtime communication.

## GitLab

GitLab can be used for all git related activities. 

# appropriate technologies

## Postgres

Postgres got a lot of features over years, but some of them are worthy enought to take a look at.

Postgres can send events to the backend.
Of course you won't transfer a lot of data, but with this feature you can build something, having a one direction dataflow.

You have native json support, so you can build stored procedures, which are returning json objects back to the backend. 
Less data has to be transfered over the wire, and operations which are nearby the data, can be done within the database.

[example database schema of redmine][2]

## Elixir

Elixir fits to these kinds of events. 
The database driver support these kind of events on a message basis.

## Phoenix LiveView

LiveView only updates part of the HTML page, so it is possible to write SPAs without JavaScript.
Therefore it is practical to use CSS only frameworks like [Bulma][3] or [Tailwind CSS][4].

## Godot

When you consider writing a `fat client` rather building a `spa`, [godot][6] is worth a look.
The primary audience of `godot` are game developers, but if you want to build a cross plattform ui,
using game engines can fit the needs.

> This way of utilizing a weird thing seemingly unrelated due to economics of scale is not new. E.g. Tesla was built on the idea that instead of building a car using custom car batteries, they opted for the seemingly insane idea of using 7000 laptop batteries to power their car.

> I wrote this story thinking Godot was the answer to the challenges people who make large complex GUIs have. But perhaps this is actually a solution to everbody. Godot Engine adds an overhead of 20–30 MB has to a solution as far as I know. For quite moderately size applications that may be acceptable. It may seem much relative to my day-to-day editor TextMate which comes in at 30 MB. However compared to the Atom editor which comes in at a hefty 500-600 MB it is a steal.

> So why should be jump to web technologies to get cross platform GUI applications? We got a tool, Godot, that runs on all major platforms which uses minimal resources and which anyone can get started using quickly.

[Is Making Advanced GUI Applications with Godot the Future?][7]
 
# Operational considerations

* How to handle deprecations?
* Minor updates
  * New features are deactivated by default.
  * administrators gets hints about new features.
* System updates 
  * set up machines for new version.
  * set old version machines to `sync mode`
  * after `old` and `new` is in sync the `sync mode` is active.
    * write requests goes to `old`
    * read requests goes to `new`
    * If the system acts as expected, `old` can be gently shut down.
    * From now on only `new` is the only active system.

# Feature ideas

## daily

* screen sharing is not needed
* a user takes the lead, and the screen position is transfered to all participants.
* When a user is speaking, the avatar on every ticket is blinking.
* Active speaking user is shown
* lead user video is shown

## share multiple sources

* if needed you can share n sources like
  * video
  * screen 1,2,3...
* think about having a presentation (e.g. for embedded sw)
  * one camera shows your face
  * the second may be a device you are working on
  * the third camera an other device with blinking leds.
  * ...
* How to compose these different sources?
  * Should the consumer do this?

# pricing

> Workspace soll in den Bezahlmodellen an die jeweiligen Unternehmen und ihre Bedürfnisse angepasst werden. Bei einem "Business Starter" geht es mit 6 US-Dollar pro Nutzer los, "Business Plus" liegt bei 18 US-Dollar, für größere Konzerne muss einzeln verhandelt werden. Bestehende G-Suite-Verträge laufen wie gewohnt weiter, es sei denn, der Kunde entscheidet sich für den Wechsel zu Workspace.

[Google Workspace: Verknüpfung der Dienste samt neuem Design][14]

# Further reading

* [GitGud, GitHub clone entirely written in Elixir][5]
* [Open-Source-Angebote für Videokonferenzen][8]
* [Wolkenkukucksheim: Cloud-Anwender vernachlässigen die Sicherheit ihrer Endgeräte][9]
* [Atlassian übernimmt Chartio für Datenanalyse][10]
* [11 Best JIRA Alternatives In 2021 (Research Done For You)][11]
* [Top 7 Most Popular JIRA Plugins (Best Jira Add-Ons In 2021)][12]
  Good estimations for people, which needs more than the jira feature deck
* [Godot User Interface Tutorials][13]
* [RethinkDB: why we failed][15]
* [Lyra - enabling voice calls for the next billion users ][16]
* [Streaming via WebRTC][17]
* [Swimlanes.io][18]

> If you do set out to build a developer tools company, tread carefully. The market is filled with good alternatives. User expectations are high and prices are low. Think deeply about the value you’re offering to the customer. Remember – wanting the world to be a certain way doesn’t make it so.

> Pick a large market but build for specific users.

> Learn to recognize the talents you’re missing, then work like hell to get them on your team.

> Read The Economist religiously. It will make you better faster.

[1]: https://www.atlassian.com/migration/journey-to-cloud
[2]: https://www.redmine.org/projects/redmine/wiki/DatabaseModel
[3]: https://bulma.io/
[4]: https://tailwindcss.com/
[5]: https://elixirforum.com/t/gitgud-github-clone-entirely-written-in-elixir/12920
[6]: https://godotengine.org/
[7]: https://medium.com/swlh/what-makes-godot-engine-great-for-advance-gui-applications-b1cfb941df3b
[8]: https://www.deutschlandfunk.de/jitsi-und-big-blue-button-open-source-angebote-fuer.684.de.html?dram:article_id=476375
[9]: https://www.deutschlandfunk.de/it-sicherheitsmesse-it-sa-cloud-anwender-vernachlaessigen.684.de.html?dram:article_id=460868
[10]: https://www.heise.de/news/Atlassian-uebernimmt-Chartio-fuer-Datenanalyse-5067351.html
[11]: https://www.softwaretestinghelp.com/jira-alternatives/
[12]: https://www.softwaretestinghelp.com/jira-plugins-addons/
[13]: https://www.youtube.com/playlist?list=PLhqJJNjsQ7KGXNbfsUHJbb5-s2Tujtjt4
[14]: https://www.heise.de/news/Google-Workspace-Verknuepfung-der-Dienste-samt-neuem-Design-4920957.html
[15]: https://www.defmacro.org/2017/01/18/why-rethinkdb-failed.html?zarsrc=30&utm_source=zalo&utm_medium=zalo&utm_campaign=zalo
[16]: https://opensource.googleblog.com/2021/04/lyra-enabling-voice-calls-for-next-billion-users.html
[17]: https://github.com/sepfy/pear
[18]: https://swimlanes.io/
[19]: https://www.heise.de/news/Zusammenarbeit-MS-Teams-als-Lockangebot-in-eine-geschlossene-Microsoft-Umgebung-6030514.html
[20]: https://matrix.org/
[21]: https://github.com/vector-im/element-web
[22]: https://plantuml.com/
[23]: https://graphviz.org/
[24]: https://app.diagrams.net/
[25]: https://about.gitlab.com/
[26]: https://www.jenkins.io/
