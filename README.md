# A Blog

A collection of writings between two friends.

### Prerequisites
To run this site locally, you need to have Ruby and Jekyll installed. More up-to-date instructions can be found [here](https://jekyllrb.com/docs/installation/#requirements).

### Setting up
```
git clone git@github.com:anotherminh/blog.git
cd blog
bundle
```

### Create a new post

This project is installed with [jekyll-compose](https://github.com/jekyll/jekyll-compose), which means there are handy commands for managing the blog.

You can create a new post as a draft by running the following command:
```
be jekyll draft "My New Post"
```

To publish your draft when ready:
```
bundle exec jekyll publish _drafts/my-new-post.md
```
