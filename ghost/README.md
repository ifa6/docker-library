# Ghost

Ghost is a free and open source blogging platform written in JavaScript and distributed under the MIT License, designed to simplify the process of online publishing for individual bloggers as well as online publications.

> [wikipedia.org/wiki/Ghost_(blogging_platform)](http://en.wikipedia.org/wiki/Ghost_%28blogging_platform%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/c5b6d94dc8f0557925ab37ca43141c0efc5cc363/ghost/logo.png)

# How to use this image

```console
$ docker run --name some-ghost -d ghost
```

This will start a Ghost instance listening on the default Ghost port of 2368.

If you'd like to be able to access the instance from the host without the container's IP, standard port mappings can be used:

```console
$ docker run --name some-ghost -p 8080:2368 -d ghost
```

Then, access it via `http://localhost:8080` or `http://host-ip:8080` in a browser.

You can also point the image to your existing content on your host:

```console
$ docker run --name some-ghost -v /path/to/ghost/blog:/var/lib/ghost ghost
```

Alternatively you can use a [data container](http://docs.docker.com/userguide/dockervolumes/) that has a volume that points to `/var/lib/ghost` and then reference it:

```console
$ docker run --name some-ghost --volumes-from some-ghost-data ghost
```