---
title: Folivo Privacy Policy
description: What Folivo does and does not do with your data.
---

# Folivo Privacy Policy

**Effective date:** October 24, 2026
**App:** Folivo (`com.folivo.folivo`)
**Platform:** Android

Folivo is an offline-first document workspace: a viewer and toolkit for PDFs, Office files, images and text that scans paper and merges, compresses, converts, reorganises, annotates and signs documents.

This policy explains, plainly, what Folivo does and does not do with your data. The short version: Folivo has no account, runs every document operation on your own device, collects no analytics, and never sends your documents anywhere. The app makes exactly one kind of network request — if you turn on "Recognize text" for a scan, it downloads the reading model for that language, once — and nothing else ever leaves your device unless you send it yourself.

---

## 1. Summary at a glance

- **No account or sign-in.** Folivo never asks for an email address, an account password or any other credential. The only name it ever asks for is optional: the name shown on comments you add to a Word document (see section 5).
- **The internet is used for one thing, a download.** The first time you choose a language for "Recognize text" (English or Hindi) and tap Done, Folivo downloads that language's reading model — about 8 MB — once. That is the only request the app makes on its own, and no part of any document, and no text read from one, is ever sent with it. Every typeface the editor offers is built into the app, so choosing a font never uses the network.
- **No document ever leaves your device by itself.** Viewing, scanning, merging, compressing, converting, rotating, marking up and signing all run locally, offline, with no network involved.
- **No analytics, no advertising, no tracking.** There is no analytics SDK, no advertising SDK and no crash-reporting service in the app.
- **The camera is used only to scan paper, and is asked for only when you first tap Scan.** The pictures stay on your device (a scan you save as JPG pictures also appears in your phone's Gallery — see section 4). Folivo never records sound and has no microphone permission. No location. No contacts.
- **"Recognize text" reads your scan on your phone.** Turning it on makes the PDF searchable by adding the words it reads as an invisible layer inside the same file. The reading is done by a program inside Folivo; the words are never sent anywhere.
- **Files Folivo saves say that Folivo saved them, and when.** See section 5.
- **Anything that leaves the app, you send yourself** — sharing a document, printing it, or using "Send feedback", which hands a redacted log to your own email app for you to review and send.

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
- Your phone's storage size. Settings asks Android for it (no permission is needed) only to show how much of the phone your documents take; it is not kept or sent.

The only thing that goes out is the download described in section 4 — a text-recognition model for a language. It is a request for a fixed file at a fixed address and carries nothing else about you or your files.

---

## 4. Permissions Folivo requests, and why

Folivo runs on **Android 11 and later**, and on those versions it uses exactly five
permissions:

| Permission | What it is for |
| --- | --- |
| `MANAGE_EXTERNAL_STORAGE` ("All files access") | Lets Folivo create and use its own document folder at the top level of your device's storage, and list the supported documents elsewhere on it for its file browser. See sections 5 and 7. |
| `INTERNET` | **Downloading text-recognition models, and nothing else.** See below. |
| `CAMERA` | **Scanning paper, and nothing else.** Asked for only the first time you tap Scan. See below. |
| `FOREGROUND_SERVICE` | **Keeping "Recognize text" running while the screen is off, and nothing else.** No prompt. See below. |
| `POST_NOTIFICATIONS` | **The notifications for "Recognize text", and nothing else** — its progress ("Making <name> searchable · page 3 of 7") and, when it ends, how it went. Asked for when you confirm "Recognize text", never when the app opens. You can refuse; the progress then shows inside the app. |

A second, `WRITE_EXTERNAL_STORAGE`, appears in the app's manifest but is marked as
applying only to Android 10 and older. Since Folivo does not install on those
versions, **it is never active on your device** — it is left in place for a future
release that may support older Android.

### About the internet permission

Folivo uses the internet for one thing. **"Recognize text"**, which makes a scanned
PDF searchable, needs a reading model for the language of the document. Rather than
make every copy of the app carry every language, Folivo downloads a language's model
the first time you choose that language in the "Recognize text" sheet and tap Done —
about 8 MB, once — and keeps it in the app's private storage so it is not fetched
again. (That copy is part of the app's data, so it goes if you uninstall, and would be
downloaded once more if you reinstalled and used the language again.)

**What is sent:** a request for a fixed model file, at an address built into the app,
to Hugging Face (`huggingface.co`, and its download servers under `hf.co`). Like any
request made from your device, it carries your IP address, which is how the server
knows where to send the file back. The app identifies itself only as "Folivo".

**What is never sent:** any part of any document, and any text read from one. Any file
name. Anything about you, your library, or how you use the app. Folivo has no analytics
and no server of its own, so there is nowhere for such data to go even in principle.

Every downloaded file is checked against a fixed fingerprint built into the app and is
thrown away if it does not match.

Everything else in Folivo works with no network at all. Opening, reading, scanning,
converting, compressing, merging, signing and exporting are entirely offline, and every
typeface the editor offers is built into the app. If you never turn on "Recognize text",
Folivo never makes a network request. Scanning and saving never need the internet
either — if you are offline when you ask for searchable text, the scan is saved as
normal, and Folivo says that the searchable text needs the internet once to set up the
language and offers to try again.

Note for the curious: `INTERNET` is what Android calls a *normal* permission. It is
granted when the app is installed, never shows a prompt, and does not appear in your
phone's permission screen — which is why you do not see it listed there for this or any
other app. On the Play Store listing it appears under *Other* as "full network access".

### About the storage permission

**Please read this part, because the permission sounds broader than what Folivo does with it.**

"All files access" is, technically, a powerful permission — Android grants it as blanket access to shared storage. Folivo uses it for two things: **creating and managing its own `Folivo` folder** and the documents you put there, and listing the names, sizes and dates of the supported documents elsewhere on your storage so that its file browser can show them (see section 7). Folivo does not open or read the other files on your storage, and finding those documents opens no file and changes nothing.

**This permission is not what lets files into the app from other apps.** Opening a document that way needs no permission at all:

- Sharing a file to Folivo, or "Open with", passes that one file to Folivo with a temporary read grant from Android.
- Picking a file opens Folivo's own file browser, which lists the supported documents it found on your phone (see above) and passes on only the ones you choose. Its "Other apps" button opens Android's own system file picker instead, and picking pictures uses Android's own Photo Picker. Both of those hand over only what you select, and neither needs a permission. The system file picker is told which kinds of file Folivo can open, so it lists only those.

When a document comes in this way, Folivo keeps its own copy in its `Folivo/Documents` folder so that it is part of your library; the original stays where it was. See section 5.

At present Folivo requires this permission to start, because the document folder is where the library lives.

### About the camera permission

Folivo asks for **camera access** for one thing: the "Scan paper" scanner, which shows what the camera sees, outlines the page and takes the picture. It is a normal permission prompt, and **it appears only the first time you tap Scan**, after a short explanation of Folivo's own — never when the app opens and never during the welcome tour.

- The pictures stay on your device. They are held in the app's private cache while you scan, saved as a PDF — or, if you choose, as JPG pictures — in Folivo's own `Scans` folder, and the cache copies are deleted once the scan is saved. If you leave a scan unfinished, its pictures stay in the cache so you can carry on later, until you save it or discard it.
- **A scan saved as JPG pictures also appears in your phone's Gallery.** Folivo tells Android's media index about the pictures it has just saved, so photo apps — and any photo backup you have switched on — can see them like any other picture on your phone. A scan saved as a PDF is not added to the Gallery.
- Folivo does not upload them, and does not analyse them anywhere but on your phone — finding the page's edges is done by the app itself, with no service involved.
- If you say no, nothing else changes: you can add pictures you already have ("Add from photos", or Tools → Photos to PDF) and make a PDF from those, which needs no permission at all. You can switch the permission on later in your phone's Settings.
- A phone with no camera can still install and use Folivo; only live scanning is unavailable.

### About text recognition, the foreground service and notifications

When you turn on **Recognize text** while saving a scan, Folivo first saves the scan as usual, then reads the words from the page pictures **on your phone** and rebuilds the PDF with those words added as an invisible layer, so the document can be searched and copied from. It works on a limited amount of text at a time — ten "units", where an ordinary page counts as one and a page of small print or a newspaper counts as four, so about ten ordinary pages or fewer if some are dense — in English or Hindi. If a scan has more than that, Folivo asks you to choose which pages to read; it never reads just the first few. This can take a while, so Folivo asks Android to keep it running with the screen off (a *foreground service*, which Android requires to show a notification) and shows "Making <name> searchable · page 3 of 7". When it ends, one more notification says how it went ("<name> is now searchable", or that it could not be done). Both show the scan's name, so — depending on your phone's notification settings — they can appear on the lock screen. If Android stops the work after a few minutes, or you close the app, Folivo continues the next time you open it.

- The words read are written into the PDF on your device and nowhere else. They are not uploaded and not kept anywhere else.
- While it works, copies of your page pictures are held in the app's private storage, which other apps cannot read, and deleted when it finishes. If it does not succeed, they are kept until you tap Retry or next open the app, and then deleted. These working copies are not encrypted — including for a scan you protected with a password.
- A scan with a **password** is otherwise protected the same way as ever: the password is kept in memory only and never written down, the finished file is locked before it is saved, and if the app is closed before it finishes, the locked file you saved stays exactly as it was.
- If anything goes wrong, your saved scan is left exactly as it was.

**Permissions Folivo does not request:** microphone, photo/media library, location, contacts, call logs, SMS, or access to your other apps.

---

## 5. Where Folivo keeps your documents, and what it writes into them

Your documents live in a folder named **`Folivo`** at the top level of your device's internal shared storage — the same level as `DCIM`, `Download` and your other apps' folders. The full path is usually:

```
/storage/emulated/0/Folivo/
├── Documents/   your document library, and anything you convert or compress
├── Images/      pages exported with Convert → Images, and photos you resize
                 with Resize photo
├── Scans/       documents created with "Scan paper" (a PDF, or JPG pictures)
└── .trash/      anything you have deleted, until it is purged (section 6)
                 (kept under Documents/, Images/ or Scans/ to match where
                  it came from, so restoring puts it back where it was)
```

Everything Folivo produces goes into one of these. When you convert a document
to images, the pages land in `Images/`, and so does a photo you resize; a scan
lands in `Scans/`; everything else — a converted, compressed, merged, signed or
marked-up file — lands in `Documents/` next to your library. Folivo does not
write your files anywhere else on your device, except the copies you ask for:
a scan saved as JPG pictures also appears in your Gallery (section 4), and
**Save to Photos** (below).

**A document you open from elsewhere is copied in.** When a file reaches Folivo
through "Open with", sharing, or the file picker, Folivo copies it into
`Documents/` so that it is part of your library, and works on that copy. The
original stays where it was, untouched. The copy is an ordinary file in the
`Folivo` folder, so everything below about that folder applies to it.

This location is a deliberate choice, and it has a consequence worth understanding:

**Your documents are visible to other apps and to any file manager**, because they sit in shared storage rather than in Folivo's private area. That is the point — they are your files, you can reach them with any tool, and they are not locked inside one app.

### Folivo marks the files it produces

When Folivo writes a file — a conversion, a compression, a merge, a signed or
marked-up document — it records itself in that file's metadata, using the
ordinary fields every document format has for the purpose:

- **PDFs** get `Creator` and `Producer` set to "Folivo", plus an internal
  `FolivoEdited` flag. Nothing else — no date is added.
- **Word, Excel and PowerPoint files** get `Application` set to "Folivo", the
  same flag as a custom property, and a second custom property,
  `FolivoEditedAt`: **the date and time of the save, with your phone's time-zone
  offset** (for example `2026-10-17T10:15:00+05:30`).
- **A spreadsheet saved from Folivo's spreadsheet editor** also records
  "Last modified by: Folivo" and the time of the save in its standard
  properties. The original author, title and created date are kept as they were.
- **Images, text, CSV and HTML** cannot carry metadata, so nothing is written
  into them. Folivo notes it in its own library instead.

This is how the app can show you which documents have been through it, and it
is the same field other apps read when they tell you what produced a file.

**This is worth knowing because it travels with the file.** If you share one of
these documents, whoever receives it can see it was produced with Folivo — and,
for a Word, Excel or PowerPoint file, when it was last saved and the time zone
your phone was set to. That is all that is written: **no device name, no account,
no location, nothing else about you** — because Folivo holds none of those to
write.

### Photos you resize

**Tools → Resize photo** makes a smaller copy of one photo or signature so it
fits the size limit of a job or exam form. It runs entirely on your phone. You
pick the photo with Android's Photo Picker (no permission); Folivo works on a
copy of it, and **your original is never changed**. The result is a new JPG
saved in `Folivo/Images/`, named after the photo and the limit (for example
`photo_30KB.jpg`), and it appears in your library.

- **Nothing hidden is kept in the result.** The new file has no GPS location,
  no camera or phone model, no date taken, no thumbnail and no colour profile
  — only the plain picture. Folivo's mark (above) is **not** written into it;
  for a picture it is recorded in Folivo's own library only.
- **The name and date you add on a strip are not saved anywhere.** They exist
  only while the screen is open and in the picture itself; they are not kept in
  Folivo's settings, library, diagnostic log or any file name.
- **Save to Photos is optional and only happens when you tap it.** It puts one
  extra copy of the result into your phone's Gallery, in a folder called
  `Pictures/Folivo`, so photo apps — and any photo backup you have switched
  on — can see it. It needs no permission. Folivo does nothing with that copy
  afterwards, and deleting it from the Gallery does not delete the file in
  `Folivo/Images/`.

### Comments you add to Word documents

If you write a comment on a Word document, Folivo asks once for the name to show
on your comments. It is optional — skip it and your comments are signed
"Author". The name is kept in the app's private settings for next time, and it
is written into the document with each comment, together with the comment's
date and time, exactly as Word itself records a comment's author. Anyone you
share that document with will see it. You can type any name you like; Folivo
does not check it against anything.

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
| `Folivo/Documents/` — your documents, including the copies of files you opened from elsewhere | The library index (which documents you have, where you were reading, when you last opened each, which are bookmarked) |
| `Folivo/Images/` — pages you exported as images, and photos you resized | Your saved signatures |
| `Folivo/Scans/` — your scans | App settings and preferences, including the name you use on Word comments |
| `Folivo/.trash/` — anything deleted but not yet purged | Notes you wrote for presentation slides |
| `Pictures/Folivo/` — any copy you saved with Save to Photos | Your recent searches |
| | The diagnostic log |
| | Thumbnail and working-file caches |
| | Edits staged but never saved, and an unfinished scan |
| | Text-recognition models downloaded for a language, and the working files of a scan being made searchable |
| | How often you have used each tool |

Two things follow that you should know:

- **Deleted documents are not gone straight away.** Moving a document to the trash moves the file into a hidden `.trash` folder inside `Folivo`. Folivo deletes it permanently **30 days** after it was moved there (it checks each time the app opens), or sooner if you empty the trash yourself. If you uninstall Folivo first, the trash folder stays on your device — it survives the uninstall — until you delete it yourself. If you want a document genuinely removed now, empty the trash.
- **Reinstalling picks your documents back up.** Your files are still in the `Folivo` folder, and when the app starts, and whenever you open the Files tab, Folivo looks in that folder and adds anything it recognises back into your library. So a reinstall restores your documents, though not what Folivo knew *about* them — the page you had reached, and your saved signatures, are gone with the app's own data.

If you want everything gone, delete the `Folivo` folder with a file manager after uninstalling.

---

## 7. What Folivo stores on your device

Beyond your documents, Folivo keeps the following **locally, and only locally**:

- **A library index** — the list of your documents, their locations, your reading position, when you last opened each one, when each was added to Folivo, and which you have bookmarked. Stored in the app's own private settings storage, not in a cloud. Alongside it, a list of what is in the trash and when each item was moved there.
- **A list of the documents Folivo found on your phone** — Folivo keeps a list of the names, sizes and dates of the supported documents it found on your phone (finding them opens no file and changes nothing), stored only on your phone in the app's private storage and removed on uninstall, used only to show the file browser and never sent anywhere.
- **Your saved signatures** — when you draw, type or upload a signature in the Sign feature, Folivo can save it so you can reuse it. **Up to five signatures** are kept, in the app's private settings storage: a drawn signature as its pen strokes, a typed one as the text and the font, an uploaded one as the picture. Folivo also remembers which one is your default. They are never transmitted. You can delete any saved signature from the Signatures screen, and all of them are removed when you uninstall.
- **App settings** — theme, reader preferences, whether the app lock is on and how soon it locks again, the language you last chose for "Recognize text", and the name you use on Word comments, if you have given one.
- **Slide notes** — notes you write for the slides of a presentation, kept against that document in the app's private settings storage.
- **Your recent searches** — the words of your last six searches on Home's search screen, so you can run one again with one tap. A search is kept when you press the keyboard's search key, when you open a document from its results, or when you leave a search (going back, or clearing the box) that found something. Only the words are kept: not what they found and not which document you opened. They are in the app's private settings storage; you can remove one with its ×, or all of them with "Clear all", on the search screen.
- **How often you use each tool** — a count of how many times you have started each tool from the Tools tab, so the tab can show the four you use most at the top. Only the tool and the number are kept: not which document, and not when. They are in the app's private settings storage, never sent anywhere, and removed on uninstall.
- **A diagnostic log** — recent app events, kept to help troubleshoot problems. See section 8.
- **Text-recognition models** — the model for each language you have used (English, Hindi), saved in the app's private storage so it is downloaded once. While a scan is being made searchable, its page pictures and the words read so far are kept there too, and deleted when it finishes (or, if it does not succeed, when you retry or next open the app).
- **An unfinished scan** — the pictures of a scan you have not yet saved or discarded, kept in the app's cache so you can carry on with it.
- **Caches and working files** — thumbnails, prepared copies of a document's content that make large files quicker to show again, and in-progress edits that have not yet been saved. All in the app's private storage, all removed on uninstall.

None of this is synced to a server or an account, because there is neither. **None of it is backed up either:** Folivo excludes all of its private data from Android's cloud backup and from device-to-device transfer. (Your documents in the `Folivo` folder are ordinary files in shared storage, so a backup or sync app you use for your files may include them.)

---

## 8. The diagnostic log

Folivo keeps a short local log of app events so that a problem can be described accurately if you choose to report one.

**Personal details are stripped before anything is written to the log, not when it is sent.** As each line is recorded, Folivo automatically replaces:

- file paths → `<file>.pdf` (or `<path>` when there is no extension)
- `content://` and `file://` addresses → `<uri>`
- file names ending in a document or picture extension → `<file>.docx`
- email addresses → `<email>`
- runs of nine or more digits, such as phone or account numbers → `<number>`

The file extension is kept, because it usually explains a failure and says nothing about you. **The log never records the content of your documents.** Redaction works by recognising those patterns, so it is best-effort: a document's name written without its extension — for example in the message that a scan has been made searchable — can pass through it. That is one reason the report screen shows you everything before anything is sent (section 9).

The log is stored in the app's private storage and capped in size. It starts afresh each day: entries from earlier days are deleted the first time the app opens on a new day. You can clear it at any time, and it is removed when you uninstall or clear the app's data.

---

## 9. Sending feedback — your choice, every time

If you use **Send feedback** (Settings → Send feedback), Folivo writes a text file containing the redacted log above, a short device and app summary (app version and build, whether it is a release or test build, Android version, device make and model, time zone), the time the report was made, and any note you add.

**You can read the whole report before it goes anywhere** — the app shows you exactly what would be sent.

Folivo then hands the file to **your own email app**, pre-addressed to `info.folivo@gmail.com`. If you have no email app set up, it goes to your device's share sheet instead so you can send it however you like.

**Folivo never sends this itself, and never sends anything in the background.** There is no code in the app that uploads a report, and nowhere for it to go — Folivo has no server. The app's only outbound request is the text-recognition-model download in section 4, which cannot carry a report or anything else. Your report leaves your device only if you complete the send yourself, in your own app.

---

## 10. When you hand something to another app

Some features pass your document, part of it, or what you are asking for, to another app on your phone — always because you asked for it:

- **Copy** — puts the text you selected on the system clipboard, where any app you paste into can read it. On some Android versions other apps can read the clipboard without being pasted into.
- **Share** — sends the document to whatever app you pick from Android's share sheet.
- **Print** — passes the document to Android's printing system and the print service you choose.
- **Read aloud** — passes the text being read to your device's own text-to-speech engine.
- **Open a link** — when you tap a web, email or phone link in a Word document, Folivo first shows you the whole address and asks. Only if you choose Open does it pass that address to your browser or email app, or the number to your phone's dialler, which then opens it. The dialler only shows the number; Folivo never places a call. Folivo itself makes no request, and nothing else from the document is passed on.
- **Send feedback** — as described above.

Once a document reaches another app, it is governed by *that* app's privacy practices, not this policy. Folivo has no visibility into, or control over, what happens next.

---

## 11. Protecting the app itself

Folivo offers an optional **app lock**, which requires your phone's own unlock — PIN, pattern, password or biometric — before the app opens, and again when you come back to it after the time you choose under Settings → Auto-lock threshold: straight away, or after 1, 5 or 15 minutes away (5 unless you change it). "Straight away" includes coming back from the screens Folivo hands you to, such as the photo picker or the share sheet.

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

The app is built with open-source libraries (for PDF rendering, document parsing, the camera, finding a page's edges, text recognition, printing, text-to-speech and similar), and it carries its own fonts. These run on your device as part of the app; none of them is a service, and none reports anything.

**One third party receives a request from the app:** Hugging Face (`huggingface.co`
and its download servers under `hf.co`), when you first use a text-recognition
language, as described in section 4. That request is handled under Hugging Face's own
privacy policy. It carries no document content and no information about you beyond the
IP address any internet request necessarily reveals. If you never turn on "Recognize
text", the app never contacts it.

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

- **Delete a document** — moves it to the trash inside the `Folivo` folder, where it is permanently deleted after 30 days.
- **Empty the trash** — permanently deletes those files from your device straight away.
- **Delete a saved signature** — from the Signatures screen, at any time.
- **Forget your recent searches** — on the search screen, one at a time with its ×, or all with "Clear all".
- **Clear the diagnostic log** — from Settings → Send feedback.
- **Remove everything** — uninstall the app, then delete the `Folivo` folder with any file manager.

---

## 16. Disclaimer and limitation of liability

Folivo is provided "as is". While it is designed so that your documents are processed and stored locally rather than on a server, no software can guarantee absolute security, and the developer cannot control the security of your device, your Android version, or any other app you choose to send a file to.

To the maximum extent permitted by applicable law, the developer disclaims liability for any indirect, incidental or consequential loss arising from use of the app, from a device being lost, stolen or compromised, or from data shared by your own action. Nothing here limits any right that applicable consumer-protection or data-protection law does not allow to be limited.

This policy describes Folivo's actual behaviour as implemented on the effective date above, verified against the application's source code. It is provided for transparency and **does not constitute legal advice, and has not been reviewed by a lawyer.** An independent legal review is recommended before relying on it for regulatory purposes in any particular jurisdiction.

---

## 17. Changes to this policy

If Folivo's data practices change — for example if a future version adds crash reporting, or an optional cloud feature — this policy will be updated and the effective date above will change. Material changes will be described in the app's release notes.

---

## 18. Contact

Questions about this policy or Folivo's data practices:

**info.folivo@gmail.com**
