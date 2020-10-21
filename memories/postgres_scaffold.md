```
id: 1f2571dd-5f1f-432d-9c3e-369d5c001476
title: postgres scaffold
links:
  - e94746f6-3b6f-11ea-a29f-336b2dc2999d
```

I thought about starting a database based project recently, as I took a look at recent aproaches.
Developing a database has some generic parts.
These parts can be described within a script, which can help you to make some kind of `rapid database development`.

# loose thoughts

Use a docker container like 

```
docker run --rm -d --name project \
		-e POSGRES_PASSWORD=password \
		-e POSTGRES_HOST_AUTH_METHOD=trust postgres
```

After

```
docker stop project
```

the container will be gone.

# During start

* inject a init sql file
* make some DDL/DML/DCL
* make some seeds

# During gently shutdown 

* generate a graphical db schema
* show DDL commands 
* show some table contents
* get a pdf out of the container 

This should be a kind of report.

As for this a `custom postgres image` is needed, because aditional tools like `dot` are needed.

Make this custom image available via docker hub.

# scaffold

* genrate script
  * mkdir project
  * mkdir project/docker-entrypoint-initdb.d
    * store some sql
  * create Makefile
    * build
      * start docker
      * stop docker

after

```
$ cd project
$ make
```

a file like `projekt.pdf` will be available in the root folder.

# beyond

If you have a working stack, you can think about repeating task,
which might appear in a project.

* provide some generic init sql files for
  * user / role / permission system
    * oauth
    * password hashing stored procedures
  * comments
  * small wiki like systems
  * shops
  * article / price databases
  * multi tenancy
  * ...

To crazy?
