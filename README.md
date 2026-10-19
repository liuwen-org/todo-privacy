# todo 隐私说明

本仓库提供 todo Android 应用的中英双语隐私政策静态网页。当前应用内名称为 Tomato，包名为 `tech.liuwen.todo`，适用版本 `1.8_1`。

- 网页入口：`index.html`，无需构建、脚本、第三方字体或外部资源。
- 参考格式：同级 `diarynote-privacy/index.html`。
- 开发者及联系邮箱沿用该参考：`liuwen-org`、`liuwen.yeah@gmail.com`；发布前确认其仍可用于接收本应用的隐私请求。
- 本次只准备本地仓库文件；尚未推送、开启 Pages 或验证公网链接。

## 发布到 GitHub Pages

1. 将审核后的文件提交并推送到 GitHub 仓库 `liuwen-org/todo-privacy` 的 `main` 分支。
2. 在仓库 Settings → Pages 中选择 Deploy from a branch，分支选择 `main`，目录选择 `/ (root)`，保存。
3. 等待部署完成。未配置自定义域名时，预期网址为 `https://liuwen-org.github.io/todo-privacy/`，以 Pages 设置中实际显示的地址为准。
4. 使用未登录的浏览器及手机确认页面可公开访问、无地区限制、无需登录，中英文及邮箱链接显示正常。未上线验证前，不应把预期网址当作已可用地址。
5. 在 Play Console 的隐私政策字段填写已验证的 HTTPS 地址，并在应用内提供隐私政策入口。当前 Android 源码未发现指向此页面的入口，本次未修改 Android 应用。

Google Play 要求隐私政策使用公开、可访问、无地区限制的网页链接，并说明应用、开发者、数据处理、安全、保存删除及联系方式；不能只上传 PDF。政策不替代 Play Console 数据安全表单，也不保证通过审核。

## 数据安全表单核对

当前代码没有应用联网权限、广告、账号、第三方使用统计或崩溃上报；专注统计及设置保存在本地。提交时按最终发布产物和 Google Play 对“收集”“共享”的定义核对，不能照搬 DiaryNote 的 Firebase 统计申报。Android 系统备份和用户主动选择云盘的文件备份已在政策中披露，不应据此笼统承诺所有数据始终不会离开设备。

若发布前加入网络、统计 SDK、账号、同步或其他数据处理功能，应同步复核政策与数据安全表单。版本变更时核对页面适用版本和日期。

## 内容核对依据

对应同级 `todo.android` 源码：

- `app/build.gradle.kts`：包名和版本。
- `app/src/main/AndroidManifest.xml`：权限和系统备份开关。
- `app/src/main/res/xml/backup_rules.xml` 与 `data_extraction_rules.xml`：当前无额外数据排除。
- `shared/src/commonMain/kotlin/org/nsh07/pomodoro/data/Stat.kt`、`Preference.kt`、`StateRepository.kt`：统计、偏好及计时状态。
- `shared/src/androidMain/kotlin/org/nsh07/pomodoro/data/AndroidBackupRestoreManager.kt`：数据库直接导出及覆盖恢复，没有额外密码加密。
- `shared/src/commonMain/kotlin/org/nsh07/pomodoro/ui/settingsScreen/viewModel/SettingsViewModel.kt`：重置统计，不清除全部偏好。
- `gradle/libs.versions.toml`、`app/build.gradle.kts`、`shared/build.gradle.kts`：依赖核对。

官方参考：

- [Google Play 用户数据政策](https://support.google.com/googleplay/android-developer/answer/10144311?hl=zh-Hans)
- [Google Play 数据安全表单说明](https://support.google.com/googleplay/android-developer/answer/10787469?hl=zh-Hans)
- [Android 自动备份说明](https://developer.android.com/identity/data/autobackup)
