+++
title = "Chat application requirements"
headless = true
time = 30
facilitation = false
emoji= "📝"
objectives = [
    "Explain the requirements of our chat application.",
    "Explain what requirements are out of scope for our chat application.",
]
+++

We are going to make a chat application which lets multiple users exchange messages.

Let's think about the core requirements for our application:
* As a user, I can send add a message to the chat.
* As a user, when I open the chat I see the messages that have been sent by any user.
* As a user, when someone sends a message, it gets added to what I see.
* As a user, I can "like" or "dislike" someone's message.
* When messages are liked or disliked, a count of the likes and dislikes is displayed next to the message.

We can imagine other requirements too (e.g. replying to specific messages, reacting with emojis, being able to edit or delete messages, registering exclusive use of a username, ...). We will stick just to the requirements we've listed.

Because users want to see things, we know we'll need a frontend.

Because multiple users want to be able to share information (messages), we know we'll need a backend for them to communicate via.

### What we already know and what's new

Some of these requirements are similar to the quote server we've already implemented:
* Adding messages is like adding quotes.
* Seeing messages is like seeing quotes.

Others are new:
* Live updates
* Interacting with a message

First let's make a backend and a frontend to do what we already know. This shouldn't take us very long (we know how to do it, and have done it recently). It will give us a useful framework to experiment with the things that are new to us.

If we thought it would take us a long time to do what we already know, we may approach this differently. We would probably try to work out the new things first. Because they may change how we want to do everything. But because it should be quick to do what we do know, we'll start there.
