# edi-cd

GitOps inspired fleet management for embedded devices.

## Run Playbook Locally

``` bash
export MENDER_USER=MY_MENDER_LOGIN
export MENDER_PASSWORD=MY_MENDER_PASSWORD
export RUNNER_ACCESS_TOKEN=ghp_XYZ
export PLAYBOOK_MODE=run # run=apply changes, dry-run=simulate changes (default), dry-run-debug=simulate changes and show debug information
git checkout BRANCH_XY
ansible-playbook manage-fleet.yml -i inventory.yml
```

Attention: `dry-run-debug` might reveal sensitive information. Use this mode only locally.

## Secrets on GitHub

`MENDER_USER`: the Mender user (e-mail)

`MENDER_PASSWORD`: the Mender password

`RUNNER_ACCESS_TOKEN`: the GitHub access token (with repo scope) for GitHub Actions runners

## More Information

This [blog post](https://www.get-edi.io/Managing-an-IoT-Fleet-with-GitOps/) describes the GitOps inspired fleet management approach.
