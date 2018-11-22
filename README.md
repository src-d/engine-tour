# Exploring Public Git Archive with source{d} engine

Welcome to this little tour of Public Git Archive and the source{d} engine.

In this guide, we are going to run the source{d} engine locally.
An easy way to do it is by using `docker` containers.

## Quick start

First, clone this repository. (We need its `notebooks` directory.)

```bash
git clone https://github.com/src-d/engine-tour
cd engine-tour
```

Then start these two Docker containers.

```bash
docker run -d --name bblfshd --privileged -p 9432:9432 -v bblfsh-volume:/var/lib/bblfshd bblfsh/bblfshd
docker run --rm -it -p 8080:8080 -v $(pwd)/repositories:/repositories -v $(pwd)/notebooks:/home --link bblfshd:bblfshd srcd/engine-jupyter
```

This should display some logs and invite you to visit `http:/0.0.0.0:8080/`.

Click there and choose one of the notebooks available.

The notebook will provide further instructions.

Have fun!
