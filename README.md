# posthog-selfhost-build

Builds the self-hosted PostHog image from [lvlohammadi/posthog](https://github.com/lvlohammadi/posthog) and pushes it to Docker Hub.

The build runs only when started by hand: Actions, "Build self-hosted image", "Run workflow".
The fork keeps GitHub Actions switched off, so upstream PostHog changes never start a run or send a notification.

Each run pushes two tags of `<dockerhub-user>/posthog-selfhost`: `selfhost` and the dated rollback tag `sync-YYYYMMDD-<commit>`.

Settings this repository needs:

- Variable `DOCKERHUB_USERNAME`: the Docker Hub account.
- Secret `DOCKERHUB_TOKEN`: a Docker Hub access token with read and write access.
