# Testing and evaluation

The project used a combination of automated checks and structured evaluation appropriate for an Android capstone application. The latest private `develop` branch was reviewed when preparing this summary. This page avoids invented participant counts and does not reproduce private test source or internal reports.

## Automated testing

The private implementation includes tooling capable of supporting:

- Unit tests with JUnit
- Mock-based isolation with MockK
- Coroutine and asynchronous stream testing with `kotlinx-coroutines-test` and Turbine
- Controlled HTTP behaviour with OkHttp MockWebServer
- Android component tests with Robolectric
- Instrumented tests with AndroidX Test and Espresso
- Compose UI tests
- Coverage reporting with Kover

Verified areas in the latest private test suite include address validation, connection management, protocol modelling, user-facing errors, agent information, session isolation, persistence and migrations, attachments, identity and preferences, ViewModel behaviour, Markdown rendering, voice input, and accessibility semantics. The suite isolates network boundaries so most automated checks do not depend on a live relay or agent.

Coverage percentages are intentionally omitted from this portfolio because they change as the implementation evolves. Any future metric should be regenerated from the exact commit being described.

## Structured manual workflow testing

Representative end-to-end workflows include:

1. Add a valid demo agent and reopen it after restarting the app.
2. Attempt invalid or incomplete agent input and verify useful feedback.
3. Connect to an available demo agent and handle an unavailable agent safely.
4. Send and receive messages in a session.
5. Create multiple sessions, switch while a response is in progress, and verify that messages remain isolated.
6. Rename agents and sessions and verify persisted changes.
7. Cancel destructive actions and confirm that data remains intact.
8. Confirm deletions and verify that the correct agent or session is removed.
9. Exercise loading, network failure, cancellation, empty-state, and retry behaviour.
10. Exercise attachments, voice input, skills, stop-generation, and interactive approval/question flows where supported.

Use fictional messages and non-sensitive demo addresses when recording evidence.

## Peer evaluation and demonstrations

- Team members can review workflows across devices or emulator configurations.
- Peer review can check behaviour, edge cases, readability, and integration impacts.
- Tutor/client demonstrations can validate that the implemented workflows match agreed project requirements.
- Demonstration feedback can be recorded as qualitative notes without presenting it as a formal user study.

## Evidence suitable for this public repository

- Sanitised screenshots of successful workflows and important UI states
- A short screen recording using fictional data
- A high-level test matrix with pass/fail status and no confidential identifiers
- Aggregate test or coverage output only if verified and safe to disclose

Do not include private test code, raw logs, internal URLs, access tokens, real agent addresses, student identifiers, or confidential assessment feedback.
