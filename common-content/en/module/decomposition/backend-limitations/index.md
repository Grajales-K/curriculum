+++
title = "Limitations of backends"
headless = true
time = 20
facilitation = false
emoji= "📖"
objectives = [
    "Explain why a backend on its own doesn't provide reliable data persistence.",
    "Explain why we may prefer doing work in a frontend rather than backend to avoid latency.",
]
+++

We've already explored limitations of frontends.

We know a backend is just a program that runs for a long time.

### Lifetime

A major limitation of backends is that "a long time" probably isn't forever.

Sometimes we change the code of the backend. Or need restart the computer it's running on for an upgrade. Or its computer loses power and we need to start it again.

When this happens, the program starts again.

Think back to our quote server that allows users to POST new quotes.

If we had to stop the server and start it again, we would lose all of the quotes users had saved.

They're just stored in a variable, and a variable only lasts while the program it's in is running.

### Location

Another major limitation of a backend is where the code runs.

A backend's code runs on whatever server it's running on.

In contrast, a web frontend's code runs in the user's web browser.

#### Latency

One problem here is latency. Depending on where the backend and the user are physically located, it may take anywhere between 1ms and 500ms for a request to go between them.

If every time you clicked on something on a web page you needed to talk to the backend, you may need to wait half a second just for the request to travel to the server and for the response to travel back, ignoring how long it takes to actually process the request. This would be unusably slow for many applications.

#### Context

Because web frontends run in the user's web browser, they have easy access to lots of information about the user's computer. For instance, they know what language it's configured in, what time zone it's configured in, how big the browser window is, etc.

If our frontend code were instead running in a backend, the browser may need to include all of this information in every request it makes, just in case the backend needs to know it. This has a couple of drawbacks: It makes the requests bigger (which makes them slower, and maybe cost more), and it ends up sharing lots of data with the server that it may not need, which may compromise the user's privacy.

### Pull not push

A backend lives at a well-known address - we know how to connect to it. A user's web browser does not.

This means that a backend cannot try to open a connection to a user's web browser. The web browser needs to initiate the request, and then the backend can reply to the request.

Once a web browser opens a request to a backend, there are some ways to keep a bi-directional communication channel open. But the very first request needs to come from the web browser.
