## Koyeb GitHub Actions runner demo

This repository houses a simple application used to demonstrate how to deploy a GitHub Actions runner on Koyeb.

This relies on the [Koyeb GitHub runner project](https://github.com/koyeb/koyeb-github-runner).

You can read the [Deploying GitHub Actions Self-Hosted runners on Koyeb](https://www.koyeb.com/tutorials/deploying-github-actions-self-hosted-runners-on-koyeb) tutorial for more information about how to use this application.

## Using this repository

To use this repository, clone it into your own account.  [Generate a GitHub personal access token](https://github.com/settings/personal-access-tokens/new) with access to your cloned repository and "Administration" permissions set to "Read and write".

In the [Koyeb control panel](https://app.koyeb.com/), click "Create App" and select "Docker" as the deployment method.  Deploy the [`github.io/koyeb/github-runner` image](https://hub.docker.com/r/koyeb/github-runner).

Enable the "Privileged" setting in the "Deployment settings" and expand the "Advanced" section.

Set the following environment variables:

* `REPO_URL`: The URL of your GitHub clone.
* `GITHUB_TOKEN`: The GitHub personal access token you generated.
* `RUNNER_LABELS`: Set to `koyeb-runner`.  This matches the `runs-on` label of the workflow file in this repository.

Click "Deploy" when you are finished.

When a new change is detected in the repository, GitHub will dispatch the job to your GitHub runner on Koyeb.  The job will be processed and the results will be reported back to GitHub.
