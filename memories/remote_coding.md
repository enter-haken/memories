
```
id: 7dfaa434-4d1e-4357-9a10-ed8bae34f680
title: remote coding
links:
  - 038c08ea-edfb-4711-b80f-dc3fe885ea12
  - 9a9a2fb6-41b7-11ea-b332-7f561162cd24
  - bc872808-0e5b-4554-9c41-5b2883f8006b
  - b1136764-436d-11ea-9e00-8b7eebe2f57a
  - 2b57fc70-3b61-11ea-a667-c7b53685a9a8
```

Due to the Covid19 desease, software developers are send into home office. 
Since software development is not a single task any more (actually a fact for decades),
working together becomes more complicated.

Software vendors are creating colaboration functions in their products.
This leads to a kind of vendor lock in.
So if you want to use those features, all developers have to use the same dev environment.
But what if you want to use your own stack?

Similar to the the language server protocol, you can use a web view, where all changes from
every developer are shown.

# idea 

The initiator starts the session by uploading the project, which should be shared. 
During the initiating process, only files known to git 
(tracked and untracked) are uploaded.
With this aproach, the `.gitignore` file can be used 
to reduce the amount of files getting uploaded.

The client can be described as a frontend for a filesystem listener.
You start the client in the git root of your project 
and an identifier of your sesseion.
New content is uploaded, when a file got saved. 

As for the start, the participants agree to a branch to work on.
Every file gets a check sum, so changes can be identified.
Every developer, joining the session, will upload his content as well.

As for the start, the number of files should be limited.

# possible technology usage

* Elixir / Cowbowy in the backend.
* Angular in the Frontend
* Server side events (SSE) for updating the view

## pros

* no data stored on the server
* selfhosting possible (behind VPN to be more secure)

## cons

* You see no changes on every key stroke.
* Bigger projects can be a an issue due to higer memory usage. 

# Problems to solve

* Hold the entire project in memory for every user or use a database?

# Links 
* [Pair Programming simultaneously the same way that Live Share VSCode](https://intellij-support.jetbrains.com/hc/en-us/community/posts/360001795120-Pair-Programming-simultaneously-the-same-way-that-Live-Share-VSCode)
* [GitDuck](https://gitduck.com/)
* [Foobits](https://floobits.com/)
* [CodeTogether](https://www.codetogether.com/)
* [Jetbrains GitLive plugin](https://plugins.jetbrains.com/plugin/11955-gitlive)

