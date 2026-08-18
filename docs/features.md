# Feature overview

## Agent management

- Add an agent using its ConnectOnion address
- View and manage saved agents
- Connect to a selected agent
- Rename an agent
- Delete an agent through a confirmation/cancellation flow
- Retrieve agent information where the remote agent supports it

The client expects the user to already have an address. Public agent discovery is not part of the application.

## Messaging

- Send messages to a connected remote agent
- Receive and display streamed agent responses and working states
- Stop an in-progress response
- Add supported files to a message through Android's document picker
- Use voice input to compose message text
- Preserve relevant conversation state locally
- Represent connection, progress, success, and error states in the UI

## Agent-assisted workflows

- Discover and invoke agent-provided skills where supported
- Use suggested skills or slash commands from the conversation interface
- Respond to approval requests and agent clarification questions
- Handle plan-review and evaluation prompts when emitted by the remote agent
- Retain a clear user choice when an agent action requires confirmation

## Chat sessions

- Create separate chat sessions
- Switch between sessions
- Reopen previous conversations
- Rename sessions
- Delete sessions through a confirmation/cancellation flow

Sessions help users organise conversations without requiring a project-owned cloud backend. Connections and streamed events are scoped to their owning sessions so multiple conversations can make progress without mixing their messages.

## Local data and safety

- Persist relevant app, agent, and session data on the device
- Require explicit confirmation for destructive operations
- Allow cancellation before deletion
- Preserve theme and relevant app preferences
- Avoid presenting the client as an agent directory or public discovery service

## Portfolio boundaries

This page describes user-visible behaviour only. It excludes source code, private endpoint details, real agent addresses, credentials, internal project documents, and confidential test data.
