# 001-nginx-application

A static page served by Nginx in a Docker container.

## Publish to GitHub Packages

Push to `main`, or open **Actions > Build and push Nginx image > Run workflow**.
The workflow builds the [Dockerfile](./Dockerfile) and publishes to GitHub
Container Registry using the built-in `GITHUB_TOKEN`; no extra secret is needed.
Repository or organization policies must allow Actions to write packages.

Images are tagged as:

- `ghcr.io/basantashrestha/001-nginx-application:latest`
- `ghcr.io/basantashrestha/001-nginx-application:<commit-sha>`

New packages are private by default. To pull a private image locally, first
authenticate to `ghcr.io` with a personal access token (classic) with
`read:packages` scope. Alternatively, make the package public in its GitHub
package settings.

## Run the published image

```sh
docker run --rm -p 8080:80 ghcr.io/basantashrestha/001-nginx-application:latest
```

Open <http://localhost:8080>.
