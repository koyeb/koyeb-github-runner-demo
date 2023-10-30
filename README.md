## Koyeb GitHub Actions runner demo

This repository houses a simple application used to demonstrate how to deploy a GitHub Actions runner on Koyeb.

This relies on the [Koyeb GitHub runner project](https://github.com/koyeb/koyeb-github-runner).

You can read the [Deploying GitHub Actions Self-Hosted runners on Koyeb](https://www.koyeb.com/tutorials/deploying-github-actions-self-hosted-runners-on-koyeb) tutorial for more information about how to use this application.

## Using this repository

To use this repository, clone it into your own account.  [Generate a GitHub personal access token](https://github.com/settings/personal-access-tokens/new) with access to your cloned repository and "Administration" permissions set to "Read and write".

Click the "Deploy to Koyeb" button to configure the Koyeb GitHub runner deployment:

[![Deploy to Koyeb](https://www.koyeb.com/static/images/deploy/button.svg)](https://app.koyeb.com/deploy?name=github-runner&service_type=worker&privileged=true&type=docker&image=docker.io/koyeb/github-runner&env[REPO_URL]=CHANGE_ME&env[GITHUB_TOKEN]=CHANGE_ME&env[RUNNER_LABELS]=koyeb-runner&ports=8000;http;/)

Modify the values for the following environment variables:

* `REPO_URL`: The URL of your GitHub clone.
* `GITHUB_TOKEN`: The GitHub personal access token you generated.

Click "Deploy" when you are finished.

When a new change is detected in the repository, GitHub will dispatch the job to your GitHub runner on Koyeb.  The job will be processed and the results will be reported back to GitHub.
