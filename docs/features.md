# 功能说明

## Agent 管理

- 使用 ConnectOnion 地址添加 Agent
- 查看和管理已保存 Agent
- 连接指定 Agent
- 编辑和重命名 Agent
- 通过确认 / 取消流程删除 Agent
- 在远程 Agent 支持时获取其基本信息

客户端要求用户提前获得 Agent 地址，不提供公开 Agent 发现功能。

## 消息与 Streaming

- 向已连接的远程 Agent 发送消息
- 接收并展示 Streaming Response 和工作状态
- 停止正在进行的 Agent 生成，同时保持 WebSocket 连接
- 通过 Android 文档选择器添加受支持的文件附件
- 使用语音输入生成待发送文本
- 在本地保存相关对话状态
- 在 UI 中区分连接、Loading、Streaming、成功、中断和错误状态

## Stop Generation（US-25）

- Agent 工作或 Streaming 输出期间，将发送按钮切换为停止操作
- 用户点击停止后，通过当前 WebSocket 发送 `{"type":"INTERRUPT"}`
- 中断当前生成任务，不关闭 WebSocket
- Interrupt 完成后正确结束 Loading 状态
- 恢复输入框和正常发送功能
- 处理生成中、请求停止、中断完成及延迟事件等状态变化

## Agent 交互能力

- 在远程 Agent 支持时发现并使用 Skills
- 使用推荐 Skill 或 Slash Commands
- 响应 Approval 和 Agent 提问
- 处理 Plan Review、Evaluation 等远程交互事件
- 对需要用户确认的 Agent 操作保留明确选择权

## Session 管理

- 创建独立聊天 Session
- 在不同 Session 之间切换
- 重新打开历史对话
- 重命名和删除 Session
- 对删除操作提供确认 / 取消流程
- 在切换时维护正确的会话上下文和 UI 状态

连接和 Streaming 事件按所属 Session 管理，使多个会话可以分别工作，同时避免消息或状态相互混淆。

## 本地数据与操作安全

- 在设备本地保存相关 Agent、Session、消息和应用偏好
- 对破坏性操作要求用户明确确认
- 允许用户在执行删除前取消
- 保留主题等应用设置
- 不将客户端描述为 Agent 目录或公开发现服务

## Portfolio 公开边界

本文档只介绍用户可见能力，不包含源码、私有端点、真实 Agent 地址、凭据、内部项目文档或机密测试数据。

