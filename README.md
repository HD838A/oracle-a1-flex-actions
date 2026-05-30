# Oracle A1.Flex GitHub Actions Scheduler

This repository runs a GitHub Actions workflow on a schedule to attempt one Oracle Cloud `VM.Standard.A1.Flex` instance creation.

Secrets are stored in GitHub Actions repository secrets. No OCI keys, config files, or local logs belong in this repository.

## Schedule

The workflow uses GitHub Actions native `schedule` and runs every 10 minutes at minutes `7,17,27,37,47,57` every hour in UTC. These are defined as separate cron entries to make GitHub's scheduler registration explicit.

## Notifications

When an instance creation starts successfully, the workflow calls the configured Bark success URL from `BARK_SUCCESS_URL`.

## Required Secrets

- `OCI_CLI_REGION`
- `OCI_CLI_USER`
- `OCI_CLI_TENANCY`
- `OCI_CLI_FINGERPRINT`
- `OCI_CLI_KEY_CONTENT`
- `OCI_COMPARTMENT_ID`
- `AD_NAME`
- `IMAGE_ID`
- `OCI_SUBNET_ID`
- `SSH_PUBLIC_KEY`
- `BARK_SUCCESS_URL`
