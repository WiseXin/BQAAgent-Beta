# BQA_Agent_Beta 首次安装配置说明 / First-Install Setup Guide

BQA_Agent_Beta 是运行在 Android 手机上的 AI Agent（Phone-Use），通过感知与操控屏幕跨 App 执行任务。本文说明拿到安装包后，从安装到可用的完整首次配置流程。

BQA_Agent_Beta is an on-device AI agent (Phone-Use) that perceives and operates the screen to complete tasks across apps. This guide covers everything needed after you obtain the APK.

## 1. 安装 / Install

- 要求 Android 11 及以上的真机（Android 11+ 才支持无线调试配对）。
- 直接安装 APK 即可；若设备上装过其他签名的版本，需先卸载旧版再安装。

Requires a physical device on Android 11 or later (wireless-debugging pairing needs 11+). Install the APK directly; if a differently-signed version was installed before, uninstall it first.

## 2. 首次启动引导 / Onboarding

应用首次启动会依次进入：

1. **选择 LLM 供应商**：DeepSeek（默认）、OpenAI、Anthropic 或 Google。
2. **填写配置**：非 DeepSeek 需要填入官方端点（Base URL）、模型名和 API Key；DeepSeek 只需 API Key。

配置完成后进入主页。

On first launch the app walks through provider selection (DeepSeek by default, or OpenAI / Anthropic / Google) and asks for the endpoint, model name and API key. After that you land on the home page.

## 3. 启动内嵌 Shizuku 服务 / Start the Embedded Shizuku Server

BQA_Agent_Beta 内嵌了 Shizuku 服务，**无需安装官方 Shizuku app**。到达主页后若服务未就绪，会自动弹出配置向导，全程约 1 分钟：

1. 先确保手机已开启「开发者选项」（设置 → 关于手机 → 连续点击「版本号」7 次）。
2. 在向导中点击**「打开无线调试」**，应用会跳转到系统「无线调试」页面，打开该开关。
3. 返回应用，点击**「开始配对」**，应用会发出一条用于输入配对码的通知（首次会先请求通知权限，请允许）。
4. 在系统「无线调试」页面进入**「使用配对码配对设备」**，弹窗上会显示一个 6 位配对码——**此弹窗保持打开，不要关闭**。
5. 下拉通知栏，把 6 位配对码输入到应用发出的通知里，提交后等待自动返回下一步。
6. 配对成功后，向导会出现**「启动内置服务」**按钮，点击启动。
7. 服务启动后向导会提示授权，点击**「授权」**允许 BQA_Agent_Beta 控制设备。

完成上述步骤后即可免电脑控制设备；向导关闭后不会重复弹出。

No official Shizuku app is needed. When the wizard pops up on the home page, follow it step by step (~1 min):

1. Make sure Developer options is enabled (Settings → About phone → tap "Build number" 7 times).
2. Tap "Open wireless debugging" in the wizard, then switch on Wireless debugging in system settings.
3. Back in the app, tap "Start pairing" — the app posts a notification for code entry (grant the notification permission if asked).
4. In system Wireless debugging, open "Pair device with pairing code". Keep the popup with the 6-digit code **open**.
5. Pull down the notification shade, enter the 6-digit code into the app's notification and send it.
6. Once paired, tap "Start built-in service" in the wizard.
7. When prompted, tap "Grant" to allow BQA_Agent_Beta to control the device.

## 4. 验证 / Verify

在主页向 Agent 下发一条简单指令（如「打开设置」），确认屏幕出现指针动画且任务能执行，即完成首次配置。

Issue a simple command on the home page (e.g. "open Settings"). If the pointer overlay appears and the task executes, the setup is complete.
