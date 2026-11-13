# GitHub Actions Lab 9 — stage files

Copy the designated stage file to `.github/workflows/` **only when that numbered lab step is reached**. Copying the final files immediately loses the screenshot evidence of the earlier stages.

## Mapping

| Step in lab | Copy this stage file | Destination | Required screenshots |
| --- | --- | --- | --- |
| Step 2, first run | `stages/01-hello-no-checkout.yml` | `.github/workflows/hello.yml` | 3 |
| Step 2, checkout | `stages/02-hello-with-checkout.yml` | `.github/workflows/hello.yml` | 4, then manual run for 5 |
| Step 3 | `stages/03-hello-manual-only.yml` | `.github/workflows/hello.yml` | — |
| Step 3 | `stages/04-ci-basic.yml` | `.github/workflows/ci.yml` | 6 |
| Step 4 | `stages/05-ci-matrix.yml` | `.github/workflows/ci.yml` | 7, 8 |
| Step 5 | `stages/06-config-demo.yml` | `.github/workflows/config-demo.yml` | 9 |
| Step 6 | `stages/07-publish-build.yml` | `.github/workflows/publish.yml` | 10, 11 |
| Step 7 | `stages/08-publish-full.yml` | `.github/workflows/publish.yml` | 12, 13, 14 |

## Example in PowerShell

1. Download this ZIP into your Downloads folder.
2. `Expand-Archive "$HOME\Downloads\github-actions-lab-kit.zip" "$HOME\lab9-kit" -Force`
3. `cd "$HOME\actions-lab"` (the repository that you cloned)
4. `New-Item -ItemType Directory -Force .github\workflows | Out-Null`
5. `Copy-Item "$HOME\lab9-kit\stages\01-hello-no-checkout.yml" ".github\workflows\hello.yml"`
6. `git add .github; git commit -m "Add the hello workflow"; git push`
7. Capture screenshot 3 before changing to the checkout stage.

The final state of all four workflow files is supplied under `final-workflows/.github/workflows/` for review, not for copying before you finish the intermediate steps.

**Special care**
- GitHub environment `production` should have you as required reviewer and **Prevent self-review** must be unchecked if you initiated the run.
- Create branch protection **after** all workflows and tags are pushed, as Step 8 says.
- The GitHub release command here uses proper Bash line continuations (the Word document line-wrapped it).
- No real tokens/passwords should be committed; demo secret is configured in repository settings.
