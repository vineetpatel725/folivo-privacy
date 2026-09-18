---
title: Folivo Privacy Policy
description: What Folivo does and does not do with your data.
---

# Folivo Privacy Policy

**Effective date:** September 18, 2026
**App:** Folivo (`com.folivo.folivo`)
**Platform:** Android

Folivo is an offline-first document workspace: a viewer and toolkit for PDFs, Office files, images and text that merges, compresses, converts, reorganises, annotates and signs documents.

This policy explains, plainly, what Folivo does and does not do with your data. The short version: Folivo has no account, runs every document operation on your own device, collects no analytics, and never sends your documents anywhere. The app makes exactly one kind of network request — downloading a font you pick in the editor — and nothing else ever leaves your device unless you send it yourself.

---

## 1. Summary at a glance

- **No account or sign-in.** Folivo never asks for a name, email or any credential.
- **The internet is used for one thing: downloading fonts.** If you pick a font in the editor that is not already on your device, Folivo downloads that font file and keeps it for next time. That is the only request the app makes on its own. No part of any document is ever sent with it.
- **No document ever leaves your device by itself.** Viewing, merging, compressing, converting, rotating, marking up and signing all run locally, offline, with no network involved.
- **No analytics, no advertising, no tracking.** There is no analytics SDK, no advertising SDK and no crash-reporting service in the app.
- **No microphone. No location. No contacts.**
- **Anything that leaves the app, you send yourself** — sharing a document, printing it, or using "Send a problem report", which hands a redacted log to your own email app for you to review and send.

---

## 2. Who this policy covers

This policy applies to the Folivo Android application, published as an independent, privacy-first document tool.

There is no server. There is no backend, no account system, no user database and no cloud storage of your files. Folivo does not have infrastructure that *could* receive your data.

---

## 3. What Folivo does not collect

Folivo opens and edits your documents — that is what it is for — but nothing about them is gathered, sent anywhere, or seen by the developer. Specifically, the following never leave your device and are never collected:

- The content of your documents, images or files.
- Your file names, folder structure or library contents.
- Your name, email address, phone number or any account identifier — there are no accounts.
- Location data.
- Microphone input. ("Read aloud" is text-to-speech *playback*; nothing is recorded.)
- Advertising identifiers, usage analytics or tracking data of any kind.
- Crash reports. There is no crash-reporting service in this release.

The single exception to "nothing goes out" is the font download described in section 4. It carries a font name and nothing else about you or your files.

---

## 4. Permissions Folivo requests, and why

Folivo runs on **Android 11 and later**, and on those versions it uses exactly two
permissions:

| Permission | What it is for |
| --- | --- |
| `MANAGE_EXTERNAL_STORAGE` ("All files access") | Lets Folivo create and use its own document folder at the top level of your device's storage. See section 5. |
| `INTERNET` | **Downloading fonts, and nothing else.** See below. |

A third, `WRITE_EXTERNAL_STORAGE`, appears in the app's manifest but is marked as
applying only to Android 10 and older. Since Folivo does not install on those
versions, **it is never active on your device** — it is left in place for a future
release that may support older Android.

### About the internet permission

The editor lets you set text in a wide range of typefaces. Rather than bundling
hundreds of font files into the app, Folivo downloads the one you choose, the first
time you choose it, and keeps it in the app's own storage so it is not fetched
again. (That copy is part of the app's data, so it goes if you uninstall, and a
font would be downloaded once more if you reinstalled and picked it again.)

**What is sent:** a request for a font file, to Google's font servers
(`fonts.gstatic.com`). Like any request made from your device, it carries your IP
address, which is how the server knows where to send the file back.

**What is never sent:** any part of any document. Any file name. Anything about you,
your library, or how you use the app. Folivo has no analytics and no server of its own,
so there is nowhere for such data to go even in principle.

Everything else in Folivo works with no network at all. Opening, reading, converting,
compressing, merging, signing and exporting are entirely offline, and the app is fully
usable on a device that has never been online — you would simply see the fonts already
on the device rather than the wider list.

Note for the curious: `INTERNET` is what Android calls a *normal* permission. It is
granted when the app is installed, never shows a prompt, and does not appear in your
phone's permission screen — which is why you do not see it listed there for this or any
other app. On the Play Store listing it appears under *Other* as "full network access".

### About the storage permission

**Please read this part, because the permission sounds broader than what Folivo does with it.**

"All files access" is, technically, a powerful permission — Android grants it as blanket access to shared storage. Folivo uses it for one thing: **creating and managing its own `Folivo` folder** and the documents you put there. Folivo does not browse, index, scan or read the rest of your storage, and has no feature that would do so.

**This permission is not what lets files into the app.** Opening a document needs no permission at all:

- Sharing a file to Folivo, or "Open with", passes that one file to Folivo with a temporary read grant from Android.
- Picking a file uses Android's own system file picker, which hands over only what you select.
- "Scan paper" hands off to your phone's own camera app.

At present Folivo requires this permission to start, because the document folder is where the library lives.

**Permissions Folivo does not request:** camera, microphone, photo/media library, location, contacts, call logs, SMS, or access to your other apps.

**A note on camera access.** Today "Scan paper" opens your phone's own camera app, so Folivo does not declare the Android `CAMERA` permission. A future release is expected to request camera access directly, to provide in-app scanning with edge detection. If that ships, this policy will be updated first, and captured images will be handled the same way as everything else: on your device only.

---

## 5. Where Folivo keeps your documents, and what it writes into them

Your documents live in a folder named **`Folivo`** at the top level of your device's internal shared storage — the same level as `DCIM`, `Download` and your other apps' folders. The full path is usually:

```
/storage/emulated/0/Folivo/
├── Documents/   your document library, and anything you convert or compress
├── Images/      pages exported with Convert → Images
├── Scans/       documents created with "Scan paper"
└── .trash/      anything you have deleted, until you empty the trash
                 (kept under Documents/, Images/ or Scans/ to match where
                  it came from, so restoring puts it back where it was)
```

Everything Folivo produces goes into one of these. When you convert a document
to images, the pages land in `Images/`; a scan lands in `Scans/`; everything
else — a converted, compressed, merged, signed or marked-up file — lands in
`Documents/` next to your library. Folivo does not write your files anywhere
else on your device.

This location is a deliberate choice, and it has a consequence worth understanding:

**Your documents are visible to other apps and to any file manager**, because they sit in shared storage rather than in Folivo's private area. That is the point — they are your files, you can reach them with any tool, and they are not locked inside one app.

### Folivo marks the files it produces

When Folivo writes a file — a conversion, a compression, a merge, a signed or
marked-up document — it records itself in that file's metadata, using the
ordinary fields every document format has for the purpose:

- **PDFs** get `Creator` and `Producer` set to "Folivo", plus an internal
  `FolivoEdited` flag.
- **Word, Excel and PowerPoint files** get `Application` set to "Folivo", and
  the same flag as a custom property.
- **Images, text, CSV and HTML** cannot carry metadata, so nothing is written
  into them. Folivo notes it in its own library instead.

This is how the app can show you which documents have been through it, and it
is the same field other apps read when they tell you what produced a file.

**This is worth knowing because it travels with the file.** If you share one of
these documents, whoever receives it can see it was produced with Folivo. What
gets written is the word "Folivo" and a true/false flag — **no timestamp, no
device name, no account, nothing about you** — because Folivo holds none of
those to write.

### Passwords for protected documents

If you open a password-protected PDF, Folivo keeps that password **in memory,
for that session only**, so that moving from the reader into Pages, Sign,
Compress or Convert does not ask you again at every step.

It is never written to disk, never kept in the app's settings, and never added
to the library. Closing the app forgets it and you will be asked again next
time — which is the right way round. **Folivo does not store your passwords.**

---

## 6. What happens when you uninstall Folivo

**Your documents are not deleted.** This is intentional. The `Folivo` folder and everything in it stays on your device after the app is removed, so that uninstalling Folivo never costs you a file.

What is removed, and what is kept:

| Kept on your device after uninstall | Removed on uninstall |
| --- | --- |
| `Folivo/Documents/` — your documents | The library index (which documents you have, and where you were reading) |
| `Folivo/Images/` — pages you exported as images | Your saved signatures |
| `Folivo/Scans/` — your scans | App settings and preferences |
| `Folivo/.trash/` — anything deleted but not yet purged | The diagnostic log |
| | Thumbnail and working-file caches |
| | Edits staged but never saved |
| | Any fonts downloaded in the editor |

Two things follow that you should know:

- **Deleted documents are not gone until you empty the trash.** Moving a document to the trash moves the file into a hidden `.trash` folder inside `Folivo`. It stays on your device — and survives an uninstall — until you empty the trash in the app or delete the folder yourself. If you want a document genuinely removed, empty the trash.
- **Reinstalling picks your documents back up.** Your files are still in the `Folivo` folder, and when you open the Files tab, Folivo scans that folder and adds anything it recognises back into your library. So a reinstall restores your documents, though not what Folivo knew *about* them — the page you had reached, and your saved signatures, are gone with the app's own data.

If you want everything gone, delete the `Folivo` folder with a file manager after uninstalling.

---

## 7. What Folivo stores on your device

Beyond your documents, Folivo keeps the following **locally, and only locally**:

- **A library index** — the list of your documents, their locations, and your reading position. Stored in the app's own private settings storage, not in a cloud.
- **Your saved signatures** — when you draw, type or upload a signature in the Sign feature, Folivo can save it so you can reuse it. **Up to five signatures** are kept, stored as images in the app's private storage. They are never transmitted. You can delete any saved signature from the Signatures screen, and all of them are removed when you uninstall.
- **App settings** — theme, reader preferences, and whether the app lock is on.
- **A diagnostic log** — recent app events, kept to help troubleshoot problems. See section 8.
- **Downloaded fonts** — any font you picked in the editor is saved in the app's private storage so it is not fetched again.
- **Caches and working files** — thumbnails, and in-progress edits that have not yet been saved. All in the app's private storage, all removed on uninstall.

None of this is synced to a server or an account, because there is neither.

---

## 8. The diagnostic log

Folivo keeps a short local log of app events so that a problem can be described accurately if you choose to report one.

**Personal details are stripped before anything is written to the log, not when it is sent.** As each line is recorded, Folivo automatically replaces:

- file paths and `content://` / `file://` addresses → `<file>.pdf` or `<path>`
- email addresses → `<email>`
- runs of nine or more digits, such as phone or account numbers → `<number>`

The file extension is kept, because it usually explains a failure and says nothing about you. **The log never records the content of your documents.** It is stored in the app's private storage, capped in size, and removed when you uninstall or clear the app's data.

---

## 9. Sending a problem report — your choice, every time

If you use "Send a problem report", Folivo writes a text file containing the redacted log above, a short device and app summary (app version, Android version, device model, time zone), and any note you add.

**You can read the whole report before it goes anywhere** — the app shows you exactly what would be sent.

Folivo then hands the file to **your own email app**, pre-addressed to `info.folivo@gmail.com`. If you have no email app set up, it goes to your device's share sheet instead so you can send it however you like.

**Folivo never sends this itself, and never sends anything in the background.** There is no code in the app that uploads a report, and nowhere for it to go — Folivo has no server. The app's only outbound request is the font download in section 4, which cannot carry a report or anything else. Your report leaves your device only if you complete the send yourself, in your own app.

---

## 10. When you hand a document to another app

Some features pass your document, or part of it, to another app on your phone — always because you asked for it:

- **Copy** — puts the text you selected on the system clipboard, where any app you paste into can read it. On some Android versions other apps can read the clipboard without being pasted into.
- **Share** — sends the document to whatever app you pick from Android's share sheet.
- **Print** — passes the document to Android's printing system and the print service you choose.
- **Read aloud** — passes the text being read to your device's own text-to-speech engine.
- **Send a problem report** — as described above.

Once a document reaches another app, it is governed by *that* app's privacy practices, not this policy. Folivo has no visibility into, or control over, what happens next.

---

## 11. Protecting the app itself

Folivo offers an optional **app lock**, which requires your phone's own unlock — PIN, pattern, password or biometric — before the app opens.

**Folivo never sees or handles your credential.** It asks Android to show the system's own confirm-credential screen, and Android tells Folivo only whether the unlock succeeded. No fingerprint, face or passcode data ever reaches the app. This needs no permission.

**While the lock is engaged, your documents are hidden from the rest of the
system too.** Folivo marks its window secure, so the app's card in the
recent-apps switcher shows a blank window rather than whatever document you had
open, and Android refuses to screenshot or screen-record it. Both stop the
moment you unlock. (Android offers no way to have one without the other, so
screenshots are blocked for as long as the card is blanked.)

With the lock switched off, neither applies — the recents card shows your
document, as with any other app.

---

## 12. Third parties

Folivo integrates **no** third-party analytics, advertising, attribution or crash-reporting service. There is no SDK in the app that reports to anyone.

The app is built with open-source libraries (for PDF rendering, document parsing, printing, text-to-speech and similar). These run on your device as part of the app; none of them is a service, and none reports anything.

**One third party receives a request from the app:** Google's font service
(`fonts.gstatic.com`), when you choose a font that is not already on your device, as
described in section 4. That request is handled under Google's own privacy policy. It
carries no document content and no information about you beyond the IP address any
internet request necessarily reveals. If you never change a font in the editor, the app
never contacts it.

Apart from that, the only way data leaves Folivo is through an action you take yourself,
as described in sections 9 and 10.

---

## 13. Children's privacy

Folivo is a general-purpose document utility and is not directed at children. It does not knowingly collect personal information from anyone, of any age, because it does not collect personal information at all.

---

## 14. Security

Because your documents never pass through a server, the protection for your files is your device's own: Android's app sandboxing, your screen lock, and your device's disk encryption.

Two honest caveats:

- Documents in the `Folivo` folder are in **shared storage**, so other apps with storage access, and anyone who can unlock your phone, can read them. This is the trade for having your files reachable by any app and safe from an uninstall.
- Folivo's optional app lock protects the *app*, not the *files*. Someone with your unlocked phone and a file manager can still open the folder.

Keep your device's operating system current and use a screen lock.

---

## 15. Your choices

- **Delete a document** — moves it to the trash inside the `Folivo` folder.
- **Empty the trash** — permanently deletes those files from your device.
- **Delete a saved signature** — from the Signatures screen, at any time.
- **Clear the diagnostic log** — from Settings → Send feedback.
- **Remove everything** — uninstall the app, then delete the `Folivo` folder with any file manager.

---

## 16. Disclaimer and limitation of liability

Folivo is provided "as is". While it is designed so that your documents are processed and stored locally rather than on a server, no software can guarantee absolute security, and the developer cannot control the security of your device, your Android version, or any other app you choose to send a file to.

To the maximum extent permitted by applicable law, the developer disclaims liability for any indirect, incidental or consequential loss arising from use of the app, from a device being lost, stolen or compromised, or from data shared by your own action. Nothing here limits any right that applicable consumer-protection or data-protection law does not allow to be limited.

This policy describes Folivo's actual behaviour as implemented on the effective date above, verified against the application's source code. It is provided for transparency and **does not constitute legal advice, and has not been reviewed by a lawyer.** An independent legal review is recommended before relying on it for regulatory purposes in any particular jurisdiction.

---

## 17. Changes to this policy

If Folivo's data practices change — for example if a future version adds camera access, crash reporting, or an optional cloud feature — this policy will be updated and the effective date above will change. Material changes will be described in the app's release notes.

---

## 18. Contact

Questions about this policy or Folivo's data practices:

**info.folivo@gmail.com**
