# Server Utilities

How I run a server.

### git-deploy-template

```bash
git config --global init.templatedir `./git-deploy-template`
git init --bare --template `./git-deploy-template`
```

Use `git push` to update the `www` directory,
and use [pm2](https://github.com/Unitech/pm2) to restart the app.

### /etc/pm2/apps.json

First of all, I suggest all your app's code/etc/data goes to an OS unrelated
directory, like `/srv/` or something. So you can mount an independant data
disk into this directory (for the safety of your data).

This apps.json just register all your apps under coverage of `pm2`, then you can
call `/etc/init.d/pm2-init.sh restart {app}` to  restart your app.

See https://github.com/Unitech/pm2#multi-process-json-declaration for more details.
