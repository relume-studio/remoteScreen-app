# How to Use remoteScreen — Reviewer Guide

remoteScreen shows a Mac on an iPad or iPhone and lets you control that Mac by touch. This guide covers what a reviewer needs to test every feature, including the paid Touch Control subscription.

**App review has two halves and both are required.** The iPad/iPhone app cannot do anything on its own: it is a viewer. It needs the **remoteScreen Mac app** running on a Mac to connect to. Install both before you start.

---

## 1. What you need

| Item | Requirement |
|---|---|
| Mac | macOS 26.2 or later. Apple silicon or Intel. |
| iPad / iPhone | iPadOS or iOS 15.0 or later. iPad Air 2 or newer works. |
| Connection | A USB **data** cable (not a charge-only cable), **or** both devices on the same Wi-Fi network |
| Reviewer account | No account or sign-in is required anywhere in the app |

The Mac app is free and is distributed **outside the App Store**, from the project's public download page. The App Store record for this app covers the iPad/iPhone viewer only.

**https://github.com/relume-studio/remoteScreen-app/releases/latest/download/remoteScreen-macOS.dmg**

The DMG is signed with a Developer ID certificate and notarized by Apple, so it opens normally on double-click. Version 1.0 (build 2) is the matching release.

---

## 2. Install both sides

**On the Mac**

1. Open `remoteScreen-macOS.dmg` and drag **remoteScreen** into **Applications**.
2. Launch it. A welcome window explains the permissions it needs.
3. Grant the two permissions it asks for. Both are required for touch control to work:
   - **Screen Recording** — lets the app capture the screen or a window.
   - **Accessibility** — lets touches and key presses reach the Mac.
   - Screen Recording only takes effect after the app restarts. The window has a **Reopen App** button for this.
   - If the app icon does not appear in the System Settings list, drag the app icon from the welcome window straight into that list, then tick it.
4. Leave the Mac app running. It stays in the menu bar when the window is closed.

**On the iPad / iPhone**

1. Install the app from TestFlight or the App Store build you are reviewing.
2. Open it. A welcome screen explains the three ways to connect and offers a language picker.
3. Allow **Local Network** and **Camera** when asked. Local Network is used to find the Mac; Camera is only used to scan the QR code.

The app ships in 10 languages: Simplified Chinese, Traditional Chinese, English, Japanese, Korean, German, French, Italian, Spanish and Russian. The default is Simplified Chinese. Change it any time from the **gear menu** in the top-right corner of the Mac window, from **Settings** in the iPad app's top bar, or from the language row in either welcome screen.

---

## 3. Connect — the fast path (USB, recommended)

1. Connect the iPad to the Mac with a USB data cable.
2. On the iPad, tap **Trust This Computer** if iOS asks.
3. In the Mac app, choose **Wired**. It connects to the iPad automatically.
4. On the iPad the app shows **Connected to "Mac"**. Tap **Screen Mirroring** (or pick an app window) to start.

USB gives the lowest latency and needs no network at all. If the Mac app shows **Not connected**, make sure the iPad app is open and in the foreground, then press **Reconnect** on the Mac.

## 4. Connect — wireless path (QR code)

1. Make sure the Mac and the iPad are on the **same Wi-Fi network**.
2. In the Mac app, choose **Wireless**. A QR code appears.
3. On the iPad, tap **Scan** in the top-right and point the camera at the QR code.
4. Back on the Mac, a card asks whether to allow the device. Choose **Allow & Trust** to skip this step next time.
5. Pick what to share on the iPad.

The QR code contains a session token and expires when you leave the Wireless screen. If scanning fails, go back to Wireless on the Mac to show a fresh code.

---

## 5. What to test — the complete checklist

### Free: watching

- [ ] **Screen mirroring** — the whole Mac desktop appears on the iPad with low latency.
- [ ] **App window** — on the iPad, tap **App Windows** and pick one app. Only that window is shared, and the Mac window is resized to the iPad's aspect ratio.
- [ ] **Extended display** — tap **Extended Display**. A new display called "remoteScreen Display" appears in the Mac's System Settings → Displays. Drag a Mac window onto it and it shows on the iPad.
- [ ] **Keyboard** — with a hardware keyboard paired to the iPad, typing goes to the Mac. The on-screen keyboard also works.
- [ ] **Clipboard** — copy text on the iPad, paste it on the Mac, and the other way round.
- [ ] **Audio** — turn on "Play the Mac's audio on the iPad" in the iPad's Settings sheet. Mac audio plays on the iPad.
- [ ] **Switching the shared app** — change which Mac app is shared from the iPad without reconnecting.
- [ ] **Disconnect and reconnect** — stop sharing, then reconnect. A trusted device reconnects with no QR code.

### Paid: Touch Control

Touch is the only paid feature. Watching is always free.

- [ ] Before subscribing, touch the Mac screen from the iPad. The paywall appears and **no touch event is sent to the Mac**. This is intentional.
- [ ] The paywall states that the first **3 days are free**, and separately, in a prominent line, that the subscription **charges automatically when the free period ends** at USD 0.99 per month until cancelled.
- [ ] Subscribe with the sandbox Apple ID below. The purchase sheet should say **Environment: Sandbox**.
- [ ] After subscribing, touch works: **tap** = left click, **drag** = scroll, **long-press then drag** = drag a window or selection, **two-finger tap** = right click.
- [ ] Cancel from **Settings → Apple ID → Subscriptions** and confirm the paywall returns on the next touch.

**Sandbox account:** `tester1@relume.com` (storefront: United States)

Sign this account in **only** when the purchase sheet asks for it. Do **not** sign it into Settings → Apple ID on the review device: doing so replaces the device's Apple ID and can hide the sandbox purchase flow.

### Browser viewer (optional)

If a device has no app installed, the Mac can serve the same screen to a browser on the local network. Open the QR code's address in Safari on the iPad. In this mode **touch is not available** — tapping the page shows a message explaining that browser viewing is watch-only and pointing the user to the app. Keyboard, fullscreen and disconnect still work. This is by design.

---

## 6. Common questions a reviewer may hit

**The Mac shows "Not connected" over USB.** Use a data cable, keep the iPad app in the foreground, and tap Trust on the iPad. Then press Reconnect on the Mac.

**Nothing happens when I touch the screen.** That is the paywall gate working. Subscribe with the sandbox account, or watch for free without touching.

**The extended display option is greyed out.** The current Mac does not expose a virtual display — some virtual machines and remote Macs cannot. Screen mirroring and app window sharing still work.

**The iPad cannot find the Mac wirelessly.** Confirm both are on the same network and that Local Network permission is allowed for the app. Corporate and guest Wi-Fi networks often block device-to-device traffic; USB works regardless.

**The QR code is rejected.** It expired. Leave and re-enter the Wireless screen on the Mac for a new one.

**iPhone.** Only app-window sharing is offered, because the screen is too small for a full desktop. The iPhone layout is landscape.

---

## 7. Privacy and accounts

There is no account, no sign-up, and no developer server. Screen video, audio and input travel directly between the reviewer's own Mac and iPad over the local network or the USB cable, encrypted with Apple's Network framework (TLS-PSK) plus a CryptoKit HMAC-SHA256 handshake. Nothing is uploaded anywhere. The app collects no data, as declared in App Store Connect.

The app uses encryption solely to secure the link between the user's own devices, which is exempt under category 5 part 2 of the U.S. export regulations; `ITSAppUsesNonExemptEncryption` is set to `false` and no export compliance documentation is required.

---

## 8. Contacts

Reviewer contact details are in App Store Connect → App Review Information. For anything else:

**relume26@gmail.com**

Mac logs, if a reviewer needs to send them: `~/Library/Logs/remoteScreen26/`
