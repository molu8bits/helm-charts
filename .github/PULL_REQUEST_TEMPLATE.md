# Pull Request Template

## Description

Please include a summary of the change and which issue is fixed. Please also include relevant motivation and context. List any dependencies that are required for this change.

Fixes # (issue)

## Type of change

Please delete options that are not relevant.

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] This change requires a documentation update

## What this PR does / why we need it

## Special notes for your reviewer

Please make sure you test your changes before you push them.
Once pushed, GitHub Actions will run across your changes and do some initial checks and linting.
These checks run very quickly, please check the results.

## How Has This Been Tested?

Please describe the tests that you ran to verify your changes. Provide instructions so we can reproduce. Please also list any relevant details for your test configuration

- [ ] Helm linting
- [ ] Helm install

**Test Configuration**

* Helm version:
* Kubernetes version:

## Checklist

- [ ] Chart Version bumped
- [ ] Title of the PR starts with chart name (e.g. `[prometheus-vmware-exporter]`)
