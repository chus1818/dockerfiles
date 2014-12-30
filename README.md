Dockerfiles
===========

Those are the personal dockerfiles I use to build each of my development environments. 

All the dockerfiles to build a language-specific container use chus1818/root as base. This root image provides a user called developer added to sudoers which is intended to be the owner of the code and install basic development tools.

In order to use one of the generated images as an effective environment a local folder can be mounted as a volume of the container when launched. To speed up this process it is convenient to define a shell script as:

```bash
DockerContainerBash(){
  docker run -v ~/Code:/home/developer/Code -i -t $1 /bin/bash
}
```

With that the local dir ~/Code will be mounted at /home/developer/Code in the container.

Then it can be aliased:

```bash
alias dr=DockerContainerBash
```

And a bash session for a given image can be launched as follows:

```bash
dr chus1818/elixir
```
