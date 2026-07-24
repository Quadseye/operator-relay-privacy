# Privacy policy — Operator Relay

**Product:** Operator Relay (Android)  
**Last updated:** 2026-07-23  
**Internal codename:** Hermes Mobile Console (not a public brand)

This policy describes data handling for the Operator Relay Android app. The app connects your device to a Hermes Agent host that **you** operate. Operator Relay is not affiliated with or endorsed by Nous Research.

## What the app does

Operator Relay is a remote console. Prompts, tool results, approvals, and model responses are processed by **your** Hermes host and any providers you configured on that host. The app does not provide a model API or a hosted VPS.

## Data the app stores on the device

| Data | Purpose | Storage |
|---|---|---|
| Host display name and base URL | Connect to your host | On-device preferences |
| Dashboard session cookies | Stay signed in | Android Keystore–backed encrypted prefs |
| Optional saved password | Sign-in convenience (opt-in Credential Manager only) | Credential Manager; never ordinary prefs |
| Conversation drafts | Restore unfinished prompts | On-device |
| Session list cache / summaries | Offline awareness | On-device |
| AI content reports | Flag harmful AI output (Play generative-AI policy) | On-device only in this release |
| App lock timeout preference | Local app lock | On-device |

WebSocket tickets are memory-only and are not persisted.

## Data sent off the device

When you connect, the app sends authentication and operator traffic **only to the Hermes base URL you configured** (typically a private Tailscale/LAN address). That includes sign-in, session RPCs, prompts, approvals, job management, and slash commands.

Operator Relay does **not** currently send analytics, advertising identifiers, or crash reports to a vendor backend.

## Notifications

Attention notifications (approval / clarification) and connection alerts are local. Titles and lock-screen public copies are redacted. Notifications never include Approve/Deny actions.

Optional **background attention sync** (Settings, opt-in) uses on-device WorkManager to re-alert when an opaque attention envelope is still pending. Envelopes store event/host IDs only — never prompt or command text. No Firebase / vendor push is used in this release.
## AI-generated content

Responses come from your remote Hermes / providers. You can report offensive AI content in-app; reports stay on device in this release.

## Permissions

- **Internet / network state** — reach your host  
- **Biometric / device credential** — app lock and approve-once confirmation  
- **Notifications (API 33+)** — optional attention alerts  

No camera, contacts, SMS, or broad storage access.

## Account deletion

The app does not create a separate Operator Relay cloud account. Removing the app (or removing a host and clearing the local session in Settings) deletes local session material on that device. Revoke host access by rotating the Hermes dashboard password and removing the phone from your private overlay.

## Contact

- Project: private GitHub repo [Quadseye/operator-relay](https://github.com/Quadseye/operator-relay)
- For Play Store: publish a **public** copy of this policy (Gist, public privacy-only repo, or your domain) and keep it in sync with this file.

## Changes

Material changes to collection or sharing will update this document and the in-app Privacy screen before shipping.
