# Docker GitHub Pages Reader

Have a GitHub Pages repo you want to keep offline?
Instead of cloning it with all its history you can just
build this image, point it to the repo in question
and start it as needed.

Since, as of this writing, docker hub does not support passing build
args yet (still uses v1.8.4), you will need to copy the Dockerfile
or clone the repo. After that, just build an image like so:

```shell
docker build --pull --build-arg repo=user/repo.github.io -t my_fancy_image_name .
```

(This needs the Dockerfile in the current dir)

After that, you can always run the image with

```shell
docker run --rm -p 4000:4000 my_fancy_image_name > /dev/null
```

and access the GitHub Pages local server in your browser with
[http://localhost:4000/](http://localhost:4000/)
