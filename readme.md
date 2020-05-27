# Running site locally with docker

## Docker command
docker run --rm --name blog -it -p 4000:4000 -v $(pwd):/srv/jekyll jekyll/jekyll /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0"
