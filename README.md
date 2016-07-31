# Server-Side API with Node.JS

### Goal
As a developer, I want to use a Photo API in order to manage a photos list. The typical use cases are :

- fetch a photos's information
- update a photos's information
- add new photo
- delete a photo
- fetch all the photos of a given user (or mine)

So... How would you design this API? :)

### The Photo Object (mandatory fields)
A Photo is composed of:

- `id` - numeric unique id 
- `title` - photo's title composed of utf-8 characters
- `tags` - array of lowercased utf-8 characters 
- `url` - url of the photo
- `private` - accessibility flag
- `user_id` - owner's id

Note that a photo can be `private`: you must be authenticated and request for permission to access other user's private photos (authentication should be done via valid access_token as QS parameter).

### The User Object (mandatory fields)
- `id` - numeric unique id 
- `name` - user's name composed of utf-8 characters
- `username` - unique string identifier of the user (lowercased utf-8 characters)
- `profile_pic` - profile picture url


### Setup

- install dependencies (express framework for Node.JS) with `npm install`
- you can launch the server with `$ node index.js`

### Let's work

- implement sign up/sign in with facebook, import user's mandatory fields from facebook account
- given the node server bootstrap (index.js), create the specific endpoints for **C**reating, **R**eading, **U**pdating and **D**eleting a photo
- provide means for retrieving all the photos of the given user (take into consideration **permission scope** and **accessibility flag** here)
- choose appropriate database technology taking into consideration following facts:
	- frequent changes in models
	- ability for fast querying
	- ability to grow and scale horizontally
- think about the way of storing and serving photos binary data (some snippets of implementation here would be highly appreciated)
- focus more on **architecture principles** rather than actual coding. If you can code something it's a bonus, but we want to see how you would architecture the code, which areas you'll focus on
- preparing data on writes vs. querying on reads - what approach would you use ?
- think wider in terms of providing easy support for feature integration/modification, like:
	- providing full text search support via photo's title and tags
	- notificiation stream generation for followers of the user (for example notifications about new photos)
	- doing various async. tasks in the background...

*Notes:*

- the authentication part for the private photos doesn't have to be written. Just think about the interaction flow between the client and the server. But again, the snippets of implementation here would be appreciated.
- pay special attention to db scheme design and try to make querying as optimal as possible
