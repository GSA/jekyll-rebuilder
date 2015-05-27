jekyll-rebuilder
----------------

A very small ruby gem to rebuild jekyll websites in response to a github webhook.

Run it in the root of the directory that contains the jekyll site checkout like follows:

    jekyll-rebuilder --port 8000 --secret abcdefghijk &

This will then listen on http://0.0.0.0:8000/abcdefghijk/ and when that URL is hit it will
do a git pull in its current directory, and run jekyll build.

If there is a file called `_drafts_config.yml` in the root directory jekyll build will be invoked a second time using this config file with the `--drafts` flag. This allows you to automatically refresh a draft version of the site to preview posts ahead of time without requiring the ability to run jekyll serve on the machine you are writing on.
