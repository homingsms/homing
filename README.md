<p align="center">
  <img src="assets/banner.png" alt="Homing: an Android phone, turned into your SMS gateway" width="100%">
</p>

Homing turns an Android phone into an SMS gateway you control. Install the app on a phone with a SIM, then send SMS and MMS through a simple HTTP API. Delivery reports and replies come back to you as signed webhooks.

## Get started

1. **Install the app.** Download the signed APK from the Android repository's releases and install it on the phone.
2. **Pick a mode.** Use **Local** to call the phone directly over your network, or **Cloud** to pair one or many phones with [Homing Cloud](https://homingsms.com) and manage them from the console.
3. **Create an API key** in the app (Local) or the console (Cloud).
4. **Send a message.**

```bash
curl -X POST https://api.homingsms.com/api/v1/messages \
  -H "Authorization: Bearer hk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"type":"sms","to":"+15555215554","text":"Hello from Homing"}'
```

In Local mode, use `http://<phone-ip>:8080/api/v1` instead. Both modes share the same requests, responses, API keys and webhook signatures.

## What it is for

Messages your product sends to its own users and team, from your own phone and SIM: one-time codes, order and booking updates, system alerts, and replies to people who texted you first.

It is not a bulk marketing tool. Message only people who agreed to hear from you, honor opt-outs, and follow your carrier's terms and local law. Using Homing means accepting the [Terms](https://homingsms.com/legal/terms), [Acceptable Use Policy](https://homingsms.com/legal/acceptable-use) and [Privacy Policy](https://homingsms.com/legal/privacy).

## Good to know

- Homing is not on Google Play. You install the signed APK yourself.
- Many phones stop background apps. Exempt Homing from battery optimization and keep the phone charging.
- Android limits outgoing SMS, and carriers can block a SIM that sends too much. Pace your sends.

## Repository

This repository holds the README only. Each part is its own repository, cloned from its own branch.

| Folder | Branch | What it is |
| --- | --- | --- |
| `android/` | `android` | The Android app, with its built-in local API |
| `backend/` | `backend` | Homing Cloud API. The API contract is in `packages/contracts/` |
| `frontend/` | `frontend` | Homing Cloud console |

Each folder's README covers setup and development. The full API and webhook reference lives in `backend/packages/contracts/`.

## License

The Android app is licensed under Apache 2.0. See `android/LICENSE` and `android/NOTICE`.
