```
id: 5b3ced1f-3bee-4486-83f4-e3347c841bbe
title: performance test
links:
  - 038c08ea-edfb-4711-b80f-dc3fe885ea12
```

# performance test

create `docker container` for performance measurement


* elixir / cowboy
* dotnet core
* haskell
* python
* ...

# how does it work

* for each plattform
  * create a `base line` test for `max connections per second` (hello world)
  * create a simple database (user + address + appointment for example)
* generate measurement report as pdf
* copy result out of the container
* `docker compose` for every solution.
* make it public

