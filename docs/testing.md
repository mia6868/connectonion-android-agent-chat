# 测试与评估

项目结合自动化测试、结构化人工流程验证、Peer Review 和 Tutor / Client 演示。本文档基于 Private Repository 最新 `develop` 分支中的测试结构整理，不复制私有测试源码，也不使用未经验证的参与人数、可用性数据或性能指标。

## 自动化测试

Private Repository 中使用的主要测试工具包括：

- JUnit：Unit Test
- MockK：依赖隔离与行为验证
- `kotlinx-coroutines-test`、Turbine：Coroutine、StateFlow 和异步事件测试
- OkHttp MockWebServer：可控的 HTTP 响应与异常场景
- Robolectric：Android 组件的 JVM 测试
- AndroidX Test、Espresso：Instrumentation Test
- Compose UI Test：UI 语义和交互验证
- Kover：测试覆盖率报告

已验证的测试范围包括地址校验、连接管理、协议模型、错误映射、Agent 信息、Session 隔离、数据持久化与 Migration、附件、身份与偏好设置、ViewModel、Markdown、语音输入和 Accessibility Semantics。

多数自动化测试通过 Mock 或 Fake 实现隔离网络边界，不要求测试期间存在可用的实时 Relay 或 Agent。覆盖率会随代码变化，因此本 Portfolio 不展示可能过期的固定百分比。

## 结构化人工流程测试

代表性流程包括：

1. 添加有效的演示 Agent，并在应用重启后确认可以恢复。
2. 输入无效或不完整地址，检查错误提示与恢复流程。
3. 连接可用 Agent，并安全处理 Agent 不可用或网络失败情况。
4. 在 Session 中发送消息并接收 Streaming Response。
5. 创建多个 Session，在生成过程中切换，并检查消息和状态是否保持隔离。
6. 触发 Stop Generation，确认任务被中断、WebSocket 保持连接、Loading 结束且输入能力恢复。
7. 重命名 Agent 和 Session，并检查本地状态是否更新。
8. 取消删除操作，确认数据未被修改；确认删除后检查目标是否正确移除。
9. 验证 Loading、空状态、取消、错误、重试及延迟事件处理。
10. 在功能受支持时验证附件、语音输入、Skills、Approval 和 Ask User 流程。

进行公开演示或录制时，应使用虚构消息和非敏感演示地址。

## Peer Review 与项目演示

- 团队成员对主要流程、边界情况和集成影响进行交叉检查。
- UI 相关功能在 Emulator 或 Android 设备上进行流程验证。
- 通过 Tutor / Client 演示确认实现结果与阶段需求一致。
- 演示反馈作为定性改进依据，不包装为正式用户研究结论。

## 适合公开展示的测试材料

- 经过脱敏的关键流程截图
- 使用虚构数据录制的简短操作视频
- 不含内部标识的高层测试矩阵
- 基于指定 Commit 重新生成且确认可公开的汇总测试结果

不应公开 Private Repository 中的测试源码、原始日志、内部 URL、Token、真实 Agent 地址、学生信息或机密评审内容。

