# UsageWatch Privacy Policy

Last updated: 2026-10-08. This policy describes UsageWatch 0.2, which synchronizes Codex and Claude Code quota through the UsageWatch cloud service.

## Cloud mode

When you connect to a Usagewatch server, it processes your Usagewatch account identifier, named device connections, quota percentages, reset times, query times and push registration tokens. It processes an Apple account identifier only if you sign in with Apple or link Apple to an anonymous account. Quota data is linked to your account to synchronize your devices. Anonymous use still has a server-side identifier and does not keep quota data solely on the phone. Vercel hosts the API and isolated provider runtimes; Supabase stores the database. Hosting providers process infrastructure data under their own policies. A self-hosted API is operated by the server administrator you choose; the current Claude collector still uses Vercel Sandbox.

Skipping the startup sign-in page does not create a server-side anonymous account. The app explains recovery limits when you connect a provider; continuing anonymously creates the account then. Linking Apple later adds its identity to the existing account while retaining connections and devices. A conflict with another Apple-linked account does not merge or overwrite either account.

Official provider authentication state can include the provider account’s name, email address, account and organization identifiers, subscription plan/status and related billing metadata, because it preserves the provider CLI’s native login configuration. These fields are used for authentication and quota functionality, not advertising or marketing. UsageWatch does not receive your payment card or bank account details.

Apple refresh credentials, when used, Codex login credentials and Claude's native CLI authentication state are encrypted in the server database; encryption keys are held separately in server secrets. Usagewatch owner, refresh and viewer tokens are hashed at rest. Provider authorization is not a provider-issued read-only grant: Usagewatch restricts its own operations to authentication, quota reading and logout. The service does not start model tasks to measure usage.

The iPhone opens Claude's official authorization page in the system browser. The password is entered on the provider's page, not into Usagewatch. The user returns the official authorization code through Usagewatch to complete the pending cloud CLI login; the code must be excluded from ordinary logs and retained only for completion of that attempt. The isolated runtime processes the resulting native CLI authentication state, including account metadata needed by the CLI, and reads its native `/usage` interface. Reusable base images contain no account credentials. Client responses contain normalized quota data, never native provider authentication state.

The Claude connector does not require or import Mac files, Keychain entries, conversations, source code, local session history or status-line reports. Cloud quota snapshots have no conversation content or repository path. Old Mac pairing/upload records are historical; a new cloud connection requires official authorization on the phone.

## Device storage and notifications

Devices cache quota snapshots. Management credentials remain in the iPhone application's private Keychain; widgets and Watch receive separate revocable read credentials. Low-quota notifications require an explicit opt-in and iOS notification permission. APNs delivers update signals and, if enabled, quota alert text. Notifications can be disabled in the app.

An unlinked anonymous account cannot be recovered through Apple after sign-out or loss of management credentials. Connecting again requires new provider authorization. Link Apple beforehand to enable recovery through Apple sign-in. The app does not issue a separate recovery code. Settings → Account includes Delete account, with a confirmation explaining that deletion is permanent. It deletes the UsageWatch account and its online connections, quota data and device access, and queues revocation of remaining provider and Apple credentials. It does not delete your OpenAI or Anthropic account. Sign out only revokes this device’s access; it does not delete your UsageWatch account.

## Retention and deletion

The service keeps the latest snapshot for each connection and expiring authentication attempts/challenges. Apple login challenges expire after five minutes; provider attempts have the expiry returned by their login endpoint. Expired diagnostic login and alert records are removed after seven days by scheduled maintenance. Disconnecting removes online connection data and revokes Usagewatch access. Confirming Delete account in the iPhone app removes online account data and devices. Remaining provider credential/runtime cleanup is queued and retried when external services are unavailable.

Scheduled maintenance removes an anonymous account's online data when it has no Apple identity, no dashboard read for over seven days, and no valid management credential. Provider collection alone does not prevent this cleanup. Losing a phone does not cause immediate deletion: its server-side refresh grant can remain valid for a 180-day idle period, and widget/Watch activity can extend the parent grant. Accounts with a valid management credential or linked Apple identity are excluded. Provider credential/runtime cleanup is queued after online data removal.

Connector logout clears its local native login state; it is not a guarantee that OpenAI or Anthropic invalidates every previously issued token globally. Users may also manage sessions directly with their provider. Temporary provider sandboxes disable automatic filesystem snapshots and reusable base images contain no user credentials. Hosting backups can retain encrypted historical data until the operator's configured retention expires. Deletion does not promise immediate removal from every hosting backup. Historical encrypted data expires with the hosting provider’s backup retention; deletion must remain effective if an operator restores a backup.

## Contact

Usagewatch is not affiliated with Apple, OpenAI or Anthropic. It contains no advertising or cross-app tracking. For support, privacy inquiries or deletion assistance, email [previbe.ai@gmail.com](mailto:previbe.ai@gmail.com). Do not include access tokens, authorization codes, passwords or private usage exports in support messages.
