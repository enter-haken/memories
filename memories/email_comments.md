```
id: 09c642c7-60c7-4b92-ae1b-f6237d8584ef
title: email comments
links:
  - 038c08ea-edfb-4711-b80f-dc3fe885ea12
```

# email comments

comments for static websites / blogs via email

I use my [own static website generator][1] for a while now.
Normaly static websites have no comment section. 
Of course you can use stuff like [disqus][2] or create a twitter post for every blog entry,
but for this you rely on external services. 

As [book][1] uses elixir for serving the content, it should be possible to integrate 
a simple mail server into the application.

A good starting point would be [gen_smtp][3].

[1]: https://github.com/enter-haken/book
[2]: https://disqus.com/ 
[3]: https://github.com/gen-smtp/gen_smtp
