# todo Privacy Policy

This repository contains the English privacy policy webpage for the todo Android app, currently named Tomato in the app. Package: `tech.liuwen.todo`. Applicable version: `1.8_1`.

- Entry point: `index.html`; no build, scripts, third-party fonts, or external assets are required.
- Layout reference: the sibling `diarynote-privacy/index.html` file.
- Developer and contact details follow that reference: `liuwen-org` and `liuwen.yeah@gmail.com`. Confirm that the email address remains available for this app's privacy requests before publishing.
- The files have been prepared locally. They have not been pushed, deployed through Pages, or verified at a public URL.

## Publish with GitHub Pages

1. Push the reviewed files to the `main` branch of `liuwen-org/todo-privacy` on GitHub.
2. In Settings → Pages, select Deploy from a branch, choose `main` and `/ (root)`, and save.
3. Wait for deployment. Without a custom domain, the expected URL is `https://liuwen-org.github.io/todo-privacy/`; use the actual address displayed in Pages settings.
4. Verify public access without signing in, including on a phone. Check that the English text and email link work and that access has no geographical restrictions. The expected URL is not a verified live address until deployment and access checks succeed.
5. Enter the verified HTTPS URL in the Play Console privacy policy field and provide a privacy policy entry within the app. No entry pointing to this page was found in the current Android source; the Android app was not modified as part of this change.

Google Play requires a publicly accessible, non-geofenced privacy policy webpage covering the app, developer, data handling, security, retention, deletion, and privacy contact. A PDF alone is insufficient. This policy does not replace the Play Console Data safety form or guarantee review approval.

## Data safety review

The current source has no app Internet permission, advertising, accounts, third-party usage analytics, or crash reporting. Focus statistics and settings are stored locally. Complete the form according to the final release artifact and Google Play's definitions of collection and sharing; do not copy DiaryNote's Firebase analytics declarations. The policy discloses Android system backup and user-selected cloud file backups, so it does not promise that data can never leave the device.

If network access, analytics SDKs, accounts, synchronization, or other data handling are added, review both the policy and the Data safety form. Check the applicable version and date when releasing updates.

## Source references

Relevant files in the sibling `todo.android` repository:

- `app/build.gradle.kts`: package and version.
- `app/src/main/AndroidManifest.xml`: permissions and system backup settings.
- `app/src/main/res/xml/backup_rules.xml` and `data_extraction_rules.xml`: no additional data exclusions currently configured.
- `shared/src/commonMain/kotlin/org/nsh07/pomodoro/data/Stat.kt`, `Preference.kt`, and `StateRepository.kt`: statistics, preferences, and timer state.
- `shared/src/androidMain/kotlin/org/nsh07/pomodoro/data/AndroidBackupRestoreManager.kt`: direct database export and replacement on restore, without additional password encryption.
- `shared/src/commonMain/kotlin/org/nsh07/pomodoro/ui/settingsScreen/viewModel/SettingsViewModel.kt`: resetting statistics does not clear all preferences.
- `gradle/libs.versions.toml`, `app/build.gradle.kts`, and `shared/build.gradle.kts`: dependency review.

Official references:

- [Google Play User Data policy](https://support.google.com/googleplay/android-developer/answer/10144311?hl=en)
- [Google Play Data safety form guidance](https://support.google.com/googleplay/android-developer/answer/10787469?hl=en)
- [Android Auto Backup documentation](https://developer.android.com/identity/data/autobackup)
