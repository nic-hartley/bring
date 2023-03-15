# `bring`, the webring enabler

[Webring](https://en.wikipedia.org/wiki/Webring)s are cool!
I think people should make more of 'em.
So here's `bring`.

## What's a webring?

A webring is a collection of websites that all link to each other in a cycle.

For example, you and your friends may maintain personal blogs, and each have a "next blog" link that points to the next friend in sequence.
Or you might have multiple projects built by the same group of folks, and want to collect their sites into one larger entity without just having a "company website".
Or you just think webrings are cool and want to participate in one.

## What's `bring`?

The gist of it is:

- You have a website, say, `example.com`.
  Your buddy Alice has a website, `nightvalepresents.com/aliceisntdead`.
  Y'all wanna make a webring.
- You host `bring` on your server, then tweak your nginx proxy to hit `bring` first.
  `bring` forwards the request to your normal server, dynamically inserting the right webring header.
- Alice's site is static HTML hosted by a provider, not a VPS, so she can't run `bring` herself.
  But that's alright, she just needs to add a `<script>` tag to the top of her template which loads from your `bring` instance.
- You add her site to your `bring` configuration as a webring member
- Your sites now link to each other in a webring

And that's it!

You can have multiple people running `bring`; instances automatically federate with each other to ensure they all have the same, maximally up-to-date ring participants.
If any site goes down, it'll do its best to alert folks.

It also has a bunch more nice features.

## What nice extra features does it have?

A bunch!

### Multi-ringing

If you host `bring` yourself, your site can be part of multiple webrings.
(If you load it from another webring member, you'll be part of the webrings that member knows you're part of.)

If someone lands on your site from a webring, they'll exit on that same webring by default.
But they'll also be presented with a little dropdown that lets them choose another webring to explore.

### SSO

### Chatroom/forum/something

## Why's it called `bring`?

[In the same way as "web log" shortened to "blog", clearly "webring" gets shortened to "bring".](https://cohost.org/nic-hartley/post/1179381-give-me-a-name-for-t#comment-46ff374d-bc54-400c-8125-f487023a78c9)