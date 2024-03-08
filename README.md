# Objectives

- Learning and Testing Reusable Workflows


# Different Repo

- Let create new repository which call `BuildAndPushDockerImage.yml` workflow
- In the newly created repository create `.github/workflows/build_docker_image.yml`

```yaml
name: Reusable Workflow user

on:
  workflow_dispatch:

jobs:
  do-it:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Run a one-line script
        run: echo Hello, world!

  docker:
    uses: vMario/learn_ghactions_reusable_workflows/.github/workflows/BuildAndPublishDockerImage.yml@main
    with:
      image_name: my-awesome-app
      tag: $GITHUB_RUN_NUMBER
    secrets:
      registry_username: ${{secrets.REGISTRY_USERNAME}}
      registry_password: ${{secrets.REGISTRY_PASSWORD}}
```



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







CHECK  this
https://github.com/n3wt0n/ActionsTest/blob/main/.github/workflows/reusableWorkflowsUser.yml


https://blog.derlin.ch/github-actions-reusable-workflow-docker-images
https://github.com/derlin/rickroller/blob/main/.github/workflows/reusable_docker-build-and-push.yaml


https://dev.to/quartztechnology/use-reusable-workflows-to-push-images-on-github-actions-2a17

https://github.com/sumitraj0103/Letsdevops/blob/main/.github/workflows/workflow2.yml