# edi-cd

GitOps inspired fleet management for embedded devices.

## Run Playbook Locally

Without 2FA using username and password:

``` bash
export MENDER_USER=MY_MENDER_LOGIN
export MENDER_PASSWORD=MY_MENDER_PASSWORD
export RUNNER_ACCESS_TOKEN=ghp_XYZ
export INFLUXDB_HTTP_TOKEN=ABCDE
export PLAYBOOK_MODE=run # run=apply changes, dry-run=simulate changes (default), dry-run-debug=simulate changes and show debug information
git checkout BRANCH_XY
ansible-playbook manage-fleet.yml -i inventory.yml
```

By using a mender access token:

``` bash
export MENDER_ACCESS_TOKEN=MY_MENDER_ACCESS_TOKEN
export RUNNER_ACCESS_TOKEN=ghp_XYZ
export INFLUXDB_HTTP_TOKEN=ABCDE
export PLAYBOOK_MODE=run # run=apply changes, dry-run=simulate changes (default), dry-run-debug=simulate changes and show debug information
git checkout BRANCH_XY
ansible-playbook manage-fleet.yml -i inventory.yml
```

Attention: `dry-run-debug` might reveal sensitive information. Use this mode only locally.

## Secrets on GitHub

`MENDER_ACCESS_TOKEN`: the Mender personal access token

`RUNNER_ACCESS_TOKEN`: the GitHub access token (with repo scope) for GitHub Actions runners

## More Information

This [blog post](https://www.get-edi.io/Managing-an-IoT-Fleet-with-GitOps/) describes the GitOps inspired fleet management approach.
