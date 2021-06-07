```
id: bfb53060-3b64-11ea-855e-872de3eb04d1
title: elixir
links:
  - 1c4ddc26-3b6c-11ea-8a1f-d3bd2d7b8f9d
  - 7425e5ec-3b6c-11ea-ab66-339bddb9d6ee
  - 1fbb1e40-3b6d-11ea-a667-77559ebd764b
tags:
  - elixir
```

# elixir

BEAM based functional language.

# ideas

* having mnesia as redis/memcache replacement in front of a PostgreSQL database
  * writes to Postgres
  * notify for entity change
  * backend pulls new entity into mnesia
  * automatically distribution to all nodes
  * fast serve time
  * suitable for data with a lot of cold storage
  * further read: [Why isn’t mnesia the most preferred database for use in Elixir/Phoenix?][1]

# further reading

* [Learning Elixir's GenServer with a real-world example][2]
* [Building a Distributed Turn-Based Game System in Elixir][3]
* [Debugging Elixir Code: The Definitive Guide][4]

[1]: https://elixirforum.com/t/why-isn-t-mnesia-the-most-preferred-database-for-use-in-elixir-phoenix/16811/20
[2]: https://papercups.io/blog/genserver
[3]: https://fly.io/blog/building-a-distributed-turn-based-game-system-in-elixir/
[4]: https://curiosum.dev/blog/debugging-elixir-code-the-definitive-guide
