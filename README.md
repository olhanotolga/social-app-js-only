# A JS-only program with social-app-like functionality

## Description

The app utilized 2 classes: Post and SocialMediaApp.

### Post class

Post is responsible for creating instances of posts.

Posts have **properties**: name/author, title, date, text, comments, and likes.

Posts have **methods** for:

- liking a post,
- disliking a post,
- adding a new comment,
- editing the post,
- editing a comment,
- deleting a comment,
- displaying the post.

### SocialMediaApp class

SocialMediaApp initialized my social media app object.

a SM app has **properties**: name, posts (array)

a SM app has **methods**:

- **add new post** — creates a new Post instance by calling the constructor method of the Post class, gives it a unique ID and pushes to the posts array
- **delete a post** — removes a post by id
- **display all posts** — calls the method responsible for displaying the post data on every post stored in the posts array

## Using the app / Calling methods

### 1. Create a social app

`new SocialMediaApp();` returns an instance of a social app. e.g.

```javascript
const veryUniqueApp = new SocialMediaApp();
```

### 2. Create a new post

`veryUniqueApp.addNewPost(obj);` returns an instance of a post and adds it to the array of posts stored by the created social app object.

Its argument, `obj`, has the following format:

```javascript
{
	className: Post,
	name: 'Some Name',
	title: 'Some Title',
	text: 'Some Text'
}
```

For example:

```javascript
const post1 = veryUniqueApp.addNewPost({className: Post, name: 'Jill', title: 'Let me explain JS expressions', text: 'A JS expression is a piece of code that always evaluates to something, resolves in a single value...'});
```

### 3. Like and dislike a post

`post1.likePost();` — like the post

`post1.dislikePost();` — dislike the post

### 4. Edit a post

Example:

`post1.updatePost({title: 'JS expressions'});`

### 5. Manage comments

Add a new comment (examples):

`post1.addNewComment({name: 'Marc', text: 'Brilliant!'});`

`post1.addNewComment({name: 'Jed', text: 'trololo'});`

Edit a comment by its ID (IDs are automatically generated when being added to a post and can be retrieved by logging the `.comments` property on the post instance):

`post1.updateComment({id: 1, text: 'LOL'});`

Delete a comment by ID:

`post1.deleteComment({id: 1});`

### 6. Display posts

Display a single post (example):

`post1.displayPost();`

Display all posts (example):

`veryUniqueApp.displayPosts();`

### 7. Delete a post with all its comments

Example:

`veryUniqueApp.deletePost({id: 0});`
