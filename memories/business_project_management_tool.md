```
id: 070e0f90-d129-4079-b74e-8e8e17e43982
title: Project Management Tool
links:
  - 9a9a2fb6-41b7-11ea-b332-7f561162cd24
  - 0522c702-3b6f-11ea-80f9-a36b07e332d7
  - a9054dd6-3b6f-11ea-9c73-93b4117331ff
  - e94746f6-3b6f-11ea-a29f-336b2dc2999d
```

When Atlassian [announced][1], that they will stop selling on premise software, I thought about the impact.
A lot of companies are using jira and confluence, 
and there are a lot of alternatives out there.

But what are the core features of

* an issue tracker
* an agile tool
* a wiki like documentation tool?

I thought about starting from scratch, to try out some ideas.

# Postgres

Postgres got a lot of features over years, but some of them are worthy enought to take a look at.

Postgres can send events to the backend.
Of course you won't transfer a lot of data, but with this feature you can build something, having a one direction dataflow.

You have native json support, so you can build stored procedures, which are returning json objects back to the backend. 
Less data has to be transfered over the wire, and operations which are nearby the data, can be done within the database.

[example database schema of redmine][2]

# Elixir

Elixir fits to these kinds of events. 
The database driver support these kind of events on a message basis.

# Angular

Angular is still a good choice for business application. 
You can work either with websockets or with server send events (SSE).

[1]: https://www.atlassian.com/migration/journey-to-cloud
[2]: https://www.redmine.org/projects/redmine/wiki/DatabaseModel
