# Running site locally with docker

## Run local development server

```bash
docker run --rm --name blog -it -p 4000:4000 -v $(pwd):/srv/jekyll jekyll/jekyll /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0"

docker run --rm --name blog -it -p 4000:4000 -v $(pwd):/srv/jekyll jekyll/jekyll /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0 --livereload"
```

## Run raspi server

```bash
docker run --rm --name jekyll-build -d -v $(pwd)/Source/alun1111.github.io:/src danobot/jekyll-rpi /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0"
```
