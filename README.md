# Eden CI Workflow

Builds [kingbri1/eden](https://github.com/kingbri1/eden) for Linux ARM64 AppImage and Android ARM64 only.

## Usage

1. Push these workflows to this repository's default branch and enable GitHub Actions.
2. Open **Actions**, select **Build** (both platforms), **AppImage**, or **Android**, then **Run workflow**. Every remaining workflow supports manual runs.
3. Select the workflow repository branch in GitHub's **Use workflow from** dropdown. Enter the source branch from `kingbri1/eden` in the **Eden branch to build** field (`master` by default).
4. Click **Run workflow**. Download the AppImage/APK from **Artifacts** on the completed run.

Existing workflow-repository push/PR triggers and the daily nightly schedule remain enabled. Source-fork pushes do not automatically trigger this separate repository; run manually or send a `repository_dispatch` event (`master`, `pull_request`, or `tag`) with `client_payload.branch` set to the source branch.

No Forgejo, release-hosting, or custom GitHub tokens are required for these builds. APKs use the fork's default signing key unless you configure `ANDROID_KEYSTORE_B64`, `ANDROID_KEY_ALIAS`, and `ANDROID_KEYSTORE_PASS` as repository secrets (see [Android signing](docs/SECRETS.md#android)). Outputs are saved as workflow artifacts; these workflows do not publish releases. The older Forgejo setup documentation does not apply to this fork.

## Licensing

This is licensed under the GPLv3. This means that any forks of the workflow that distribute builds or binaries MUST also have their source code available under the GPLv3.