# GlitchTip

This is a meta repo for general issue tracking, wiki, and deployment information.

- [Django Backend](https://gitlab.com/glitchtip/glitchtip-backend)
- [Angular Frontend](https://gitlab.com/glitchtip/glitchtip-frontend)
- [Documentation](https://glitchtip.com/documentation)
- [Wiki](https://gitlab.com/glitchtip/glitchtip/-/wikis/home) 


# Deploy on Heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/kengurukleo/GlitchTip)

1. Deploy the app by clicking the above link and following the prompt.
2. SECRET_KEY is generated for you. Other environment variables must be entered in the app's settings. See configuration [docs](https://glitchtip.com/documentation/install#Configuration).

## Production considerations

Consider upgrading your Postgres and web dyno plan for production usage.

Most users do not need additional workers. However if you do, create a third dyno typed called extra_worker. Set the run command to `./bin/run-celery.sh`. Do not increase the "worker" dyno count because this these run with an embedded Celery beat scheduler.

## Upgrading GlitchTip

By default, the docker image tag is "latest". Click Deploy to upgrade to the latest GlitchTip docker image.
