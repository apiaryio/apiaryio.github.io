---
title: New API Blueprint tutorial
excerpt: Learning API Blueprint has never been easier.
layout: post 
date: 2015-03-25 16:00:00 +0000
author: zdenek 
published: true
comments: true
---

Everything at Apiary starts with API Blueprint and API Blueprint starts with its tutorial. Since providing superb and concise documentation is our priority, there is no other document that should stand more for our values. 
But frankly, the old tutorial was too long, unnecessary complex and wasn't complemented by blueprint examples,  real code and the rest of Apiary. This is changing right now with our new API Blueprint tutorial.

We have completely rewritten the tutorial, stripped any clutter, and saved advanced topics for later.  In addition, the new tutorial no longer relies on any upfront knowledge of Markdown. You can get started with API Blueprint in less than thousands words, counting blueprint snippets and footnotes! 

**Learning API Blueprint has never been easier** – check our new tutorial by yourself at <http://apiary.io/blueprint>.

And speaking of words – they say _"A picture is worth a thousand words"_. We think the same. This is why there is much more behind our tutorial than a simple prose with code examples. The tutorial is accompanied by two API Blueprint examples, its backend implementation tested in a continuous integration and finally, it is fully integrated within the Apiary application. 

## Same problem, two solutions
 Our new tutorial walks you though the basics of API Blueprint along with how you can build your very first blueprint. It uses an example of a polls service, which allows consumers to view polls and vote in them.
 
### HTTP API 
 The tutorial is using a _simplified_ Polls API version – without hypermedia controls and advanced API Blueprint features.
 
 The full version of this **simplified Polls API** can be found at <http://docs.pollsapi.apiary.io> or in the API Blueprint GitHub [repository](https://github.com/apiaryio/api-blueprint/blob/master/examples/Polls%20API.md).
 
### REST API
As we believe following REST constraints may bring competitive advantage in fields where API provider does not control clients we have also prepared a truly REST – _hypermedia_ – version of the Polls API. 

You can find the **hypermedia Polls API** at <http://docs.pollshypermedia.apiary.io/> or in the API Blueprint GitHub [repository](https://github.com/apiaryio/api-blueprint/blob/master/examples/Polls%20Hypermedia%20API.md)

This API offers both HAL and Siren media types through content-negotiation. If you are interested in hypermedia API design – please let us know on Twitter or in the discussion under this article – we will be happy to talk about it in-depth.

## Backend Implementation
The Polls API comes with an [example implementation](http://github.com/apiaryio/polls-api) so you can use it as a real API:

```bash
$ curl https://polls.apiblueprint.org/questions/1
```
```json
{
    "question": "Favourite programming language?",
    "published_at": "2014-11-11T08:40:51.620Z",
    "url": "/questions/2",
    "choices": [
        {
            "choice": "Swift",
            "url": "/questions/1/choices/1",
            "votes": 0
        }, {
            "choice": "Python",
            "url": "/questions/1/choices/2",
            "votes": 0
        }
    ]
}
```

We've deployed an instance of this API and it's accessible for anyone to experiment with: `https://polls.apiblueprint.org/`. You can also deploy your own instance of the Polls API to Heroku with a single click:

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/apiaryio/polls-api)

## Tested
At Apiary we care about the whole **API lifecycle**. This is why we have created a testing tool for your blueprints and APIs – [Dredd](https://blog.apiary.io/2013/10/10/No-more-outdated-API-documentation).

The Polls API implementation demonstrates the use of Dredd and as such its tested in a continuous integration as described in the [How To Test REST API with API Blueprint and Dredd](http://blog.apiary.io/2013/10/17/How-to-test-api-with-api-blueprint-and-dredd/) article. 

And yes, the badge bellow is live – just click on it to find out!

[![Circle CI](https://circleci.com/gh/apiaryio/polls-api.svg?style=svg)](https://circleci.com/gh/apiaryio/polls-api)

## Apiary Integration
Last but not least we have changed the _default blueprint_ used when you create a new API in Apiary to the simple version of Polls API. 

For the first time in Apiary history and thanks to the Polls API implementation you can experiment with Apiary inspector (call debugger) features right with the default API. When you set documentation console to _"debugging proxy"_ or _"production"_ the calls you make are hitting the implementation endpoint instead of the Apiary mock server. 

<img width="599" src="/images/2015-03-03-apiary-integration.png" alt="Apiary Integration" />

Note: The actual implementation of your API is set by the `HOST: http://polls.apiblueprint.org/` line on the top of tour blueprint.

## API Design and Lifecycle
We are striving to create the best tools to help everyone design beautiful API and guide it through its lifecycle.

The new API Blueprint tutorial and its settings represents just that. From learning API Blueprint, choosing the right API design and prototyping to documenting, implementing, testing and using an API.

Let us know how are we doing. 
