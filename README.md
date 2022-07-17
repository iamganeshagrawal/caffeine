## Local development

```bash
# clone your imported repository
# cd in the project directory
git submodule update --init --recursive
# Start local dev server
hugo server
```

## Deployment and hosting

1. Set the build command to: `hugo --gc --minify -b $CF_PAGES_URL`
2. Set the publish directory to: `public`
3. Make sure to set `HUGO_VERSION` to 0.58.2 or above (tested with 0.75.1)
3. Set the publish directory to: `public`

That's it, now your site gets deployed automatically on `git push` or when saving documents from Forestry.


## LICENSE

[MIT](LICENSE)
