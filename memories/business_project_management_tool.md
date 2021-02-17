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
* Git Integration
* Sprint planing
* Version planning
* Chat / Voice / Video (recording / streaming) / Messages
* Wiki
* Project Management
* Calendar
* Container Registry
* Build Server

# Thoughts

In the last years the phrase `mobile first` comes handy for every kind of new software products. 
Due to the covid pandemie, the next generation of software should be `remote first`.

## remote first

People, who are not sitting in the same room are working seamlessly together.
There is no difference to working on site anymore.
Sentences like `Can you hear me?` or `Can you see my screen?` belongs to the past.

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

# Further reading

* [GitGud, GitHub clone entirely written in Elixir][5]

[1]: https://www.atlassian.com/migration/journey-to-cloud
[2]: https://www.redmine.org/projects/redmine/wiki/DatabaseModel
[3]: https://bulma.io/
[4]: https://tailwindcss.com/
[5]: https://elixirforum.com/t/gitgud-github-clone-entirely-written-in-elixir/12920
[6]: https://godotengine.org/
[7]: https://medium.com/swlh/what-makes-godot-engine-great-for-advance-gui-applications-b1cfb941df3b
