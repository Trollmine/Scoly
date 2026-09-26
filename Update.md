# Scoly 5.2.8

## 5.2.8 — Grade synchronization polish

- Restored the brighter coral Scoly app header.
- Grade synchronization now upserts saved grades and uses stable notification identities, preventing unchanged grades from being announced again.
- Updated Android to version **5.2.8**, `versionCode 89`.

# Scoly 5.2.7

## 5.2.7 — Parent sync and Scoly administration

- Fixed parent-account synchronization so every renewed session reselects and verifies the active child before reading data; a missing child now preserves the cache instead of silently importing the first child's data.
- Kept the custom account strictly local by blocking manual and background PRONOTE refreshes until a linked child is selected.
- Rebuilt the license administration dashboard with the Scoly purple/coral visual system, responsive license cards, matching dialogs and automatic dark mode.
- Moved update metadata to `Trollmine/Scoly` and renamed the downloadable Android package to `Scoly.apk`.
- Updated Android to version **5.2.7**, `versionCode 88`.

# Scoly 5.2.6

## 5.2.6 — Interface consistency

- Unified Timetable, Grades, Carnet and cafeteria previous/current/next selectors with one rounded Scoly component.
- Restyled Agenda, opened discussions, message cards, Information details and cafeteria cards for Scoly Light and Dark.
- Removed remaining white PRONOTE surfaces and fixed inherited dark-on-dark text, icon tints and nested card contrast across menu pages.
- Standardized Homepage card typography, icon treatments and every **View all** arrow.
- Fixed dynamic French labels including the Homepage greeting, Personal Todo, View all, synchronization metadata and discussion counts.
- Preserved the existing PROnote Classic presentation and all synchronization/data behavior.
- Updated Android to version **5.2.6**, `versionCode 87`.

# Scoly 5.2.5

## 5.2.5 — My School Day completion

- Added fully local personal school events with optional subjects, descriptions, times and reminders.
- Added date-based Things to Bring with multiple items per day, packed state, prominent Homepage summaries and automatic expiry.
- Unified personal Todo, events and Things to Bring on the Scoly Homepage without changing synchronized PRONOTE homework.
- Added event notification deep links, duplicate-safe rescheduling and alarm restoration after a device restart or app update.
- Prevented profile synchronization from replacing a locally selected picture, including linked-account refreshes.
- Fixed the embedded ENT/ALISE sign-in page so its full form remains scrollable on different phone sizes.
- Updated Android to version **5.2.5**, `versionCode 86`.

# Scoly 5.2.4

## 5.2.4 — User-controlled profile pictures

- Removed profile-picture downloading from PRONOTE synchronization after repeated server-specific failures.
- PRONOTE profile synchronization now updates only the student name, class and school.
- A manually selected picture is never replaced, cleared or reset by automatic, manual or background synchronization.
- Kept the generic Scoly icon only as the fallback when the user has not selected a picture.
- Completed the agreed V5.2.x scope without adding Groups/shared Todo or exposing Scoly Todo in PROnote Classic.
- Updated Android to version **5.2.4**, `versionCode 85`.

# Scoly 5.2.3

## 5.2.3 — Timetable, profile picture and privacy fixes

- Synchronized PRONOTE timetables now keep both Week A and Week B as the repeating schedule after the exact downloaded dates.
- Profile-picture synchronization now resolves relative PRONOTE file URLs and uses the same signed-file request behavior as compatible open-source clients, with a fallback for older servers.
- The ENT/ALISE sign-in page now sizes itself from the real available viewport and remains scrollable above phone navigation areas.
- Removed the bundled personal avatar, personal profile defaults and sample class timetable; fresh installs now start with generic empty local data.
- Updated Android to version **5.2.3**, `versionCode 84`.

# Scoly 5.2.2

## 5.2.2 — Weekly timetable and account linking polish

- Restyled the Scoly weekly timetable with themed controls, rounded day columns, readable dark-mode lesson cards and a clear current-day state; PROnote Classic keeps its familiar layout.
- Restored the PROnote Classic drawer’s **Switch accounts** action without changing Scoly’s parent-only multiple-account entry.
- Made the PRONOTE account type visible before opening the official ENT login, preventing parent credentials from being sent to the student space.
- Updated Android to version **5.2.2**, `versionCode 83`.

# Scoly 5.2.1

## 5.2.1 — Profile and French interface fixes

- Fixed PRONOTE student-picture downloads by using the mobile session cookie and request identity expected by external PRONOTE files, with binary image-type detection.
- Restored manual editing for linked-profile names, classes, schools and pictures; local choices remain separate from synchronized source information.
- A normal profile tap opens the account chooser while a triple-tap opens the profile editor again.
- Stabilized French translation by batching dynamic translations and preventing the observer from translating its own mutations or protected user data.
- Updated Android to version **5.2.1**, `versionCode 82`.

# Scoly 5.2.0

## 5.2.0 — Personal Todo and homework continuity

- Added a Scoly-only personal Todo page, kept completely unavailable from PROnote Classic.
- Personal tasks support due dates, subjects, priorities, completion and optional Android reminders.
- Added Todo previews to the Scoly Homepage and notification deep links back to the relevant task.
- PRONOTE homework can now be marked finished even while automatic synchronization is enabled.
- Homework refresh now merges existing items by their PRONOTE identity and content instead of deleting everything, preventing duplicates and preserving each local completion state.
- Fixed profile-information synchronization so authenticated PRONOTE student pictures are downloaded with the expected mobile request identity and an older saved picture is retained if a refresh fails.
- Updated Android to version **5.2.0**, `versionCode 81`.

# Scoly 5.1.10

## 5.1.10 — Cafeteria reminders and linked profiles

- Added an optional 8:00 notification on ALISE days that are actually reservable and still need a reservation, with a direct link to the cafeteria account.
- Added PRONOTE account-type detection and native Pawnote child-resource switching for parent accounts.
- Added the Scoly account chooser from the header, with every linked child/student profile plus a preserved custom local account.
- The drawer’s Multiple accounts action is enabled only for linked parent accounts with multiple children and remains clearly unavailable otherwise.
- Added profile-information synchronization for the student name, picture, class and school, alongside the existing synchronization categories.
- Linked profile data synchronizes in its own local slot so switching back to the custom account restores its existing data and settings.
- Updated Android to version **5.1.10**, `versionCode 80`.

# Scoly 5.1.9

## 5.1.9 — Complete multi-child ALISE loading

- Fixed secondary ALISE children appearing without a balance or reservation availability.
- When ALISE does not publish a direct profile URL, Scoly now operates the official child dropdown off-screen and reuses the resulting authenticated session.
- Every child profile is verified after switching before its balance, activity and reservation calendar are merged into the native interface.
- The same verified switching path is reused for per-child reservation and cancellation actions.
- Updated Android to version **5.1.9**, `versionCode 79`.

# Scoly 5.1.8

## 5.1.8 — Reliable ALISE dashboard handoff

- Fixed the ENT sign-in handoff so any valid authenticated ALISE client page closes automatically and returns to Scoly’s native interface.
- ALISE sessions are now validated from the real family dashboard instead of relying on the separate information page.
- Added direct parsing for ALISE’s child-profile dropdown, including its selected child and available profile-switch links.
- Added a safe current-child fallback when an ALISE installation omits switch links instead of rejecting otherwise usable account data.
- Updated Android to version **5.1.8**, `versionCode 78`.

# Scoly 5.1.7

## 5.1.7 — True per-child ALISE profiles

- Replaced the shared family reservation approximation with ALISE’s real child-profile switching flow.
- Each child now displays the balance returned by their own ALISE profile.
- Reservation calendars are loaded and merged per child, so selecting another child immediately shows that child’s real reserved days.
- Removed the artificial Update action: selections with any existing reservation show Cancel; selections with none show Reserve.
- Mixed selections cancel the existing reservations of every selected child while leaving already-unreserved children unchanged.
- Reservation and cancellation requests are issued and verified separately for every selected child.
- Fixed the one-day calendar offset that produced Sundays and hid Fridays.
- Updated Android to version **5.1.7**, `versionCode 77`.

# Scoly 5.1.6

## 5.1.6 — Reliable family reservation states

- Fixed the ALISE account header parser so the establishment no longer contains the parent menu, address, children and balance.
- Restored balance extraction from ALISE’s rendered `Solde au … : … €` text when its malformed legacy markup defeats the normal field parser.
- Child selection now refreshes every reservation row immediately.
- Added full, partial, other-child and unknown-child reservation states for family accounts.
- Persisted the selected-child assignment locally while keeping ALISE’s server-side meal quantity authoritative.
- Changing the number of selected children now updates the ALISE reservation quantity, with rollback if the replacement reservation fails.
- Updated Android to version **5.1.6**, `versionCode 76`.

# Scoly 5.1.5

## 5.1.5 — Family ALISE reservations

- Added a parent-session child selector so one child or all linked children can be included in a meal reservation.
- Reservation quantities now match the number of selected children while cancellations continue to clear the existing reservation for that date.
- Replaced encrypted ALISE reservation tokens with the actual meal dates returned by the reservation calendar.
- Fixed balances and account activity to always display in euros, including when Scoly is using English.
- Cleaned up ALISE parent-account parsing so the establishment, parent and children are shown separately and French HTML entities render correctly.
- Updated Android to version **5.1.5**, `versionCode 75`.

# Scoly 5.1.4

## 5.1.4 — Correct ENT-delegated ALISE connection

- Replaced the incorrect ALISE username/password form with the school’s real ENT → CAS/EduConnect → ALISE activation flow (`USER_5`).
- The official authentication page is shown only while signing in; Scoly captures the resulting ALISE session and returns to the native balance, activity and reservation interface.
- Scoly never reads or stores the ENT password. Persistent WebView cookies allow the official ENT session to renew ALISE access when still valid.
- Removed the obsolete encrypted ALISE credential payload from upgraded installations while preserving all unrelated Scoly, PRONOTE and timetable data.
- Fixed the ALISE loading-state guard that could prevent the first native dashboard request from starting.
- Updated Android to version **5.1.4**, `versionCode 74`.

# Scoly 5.1.3

## 5.1.3 — Native ALISE accounts and reservations

- Replaced the session-expiring ALISE WebView with a native Scoly account screen instead of opening `aliIndexClient.php` without its required delegated session.
- Added one-time ALISE account linking using the school site ID, username and password; saved credentials are encrypted with Android Keystore and temporary PHP sessions renew automatically.
- Added native balance, upcoming reservation and recent account-operation views with dedicated Scoly Light/Dark and PROnote Classic presentations.
- Restored direct meal reservation and cancellation support through ALISE's existing reservation flow, including explicit confirmation and a fresh server read before Scoly reports success.
- Kept ALISE network/parsing work off the UI thread, blocked duplicate actions and retained the previous dashboard while a manual refresh fails.
- Updated Android to version **5.1.3**, `versionCode 73`.

# Scoly 5.1.2

## 5.1.2 — In-app ALISE

- Added a dedicated ALISE entry to the app's right-side tabs menu and changed cafeteria reservation actions to stay inside Scoly instead of opening the external browser.
- Added an isolated in-app ALISE browser with responsive controls, safe HTTPS navigation, cookie/session support, downloads, back/reload/close controls and clean connection errors.
- Restyled the official ALISE pages without replacing their forms or payment flow: Scoly uses coral/violet rounded light or dark styling, while PROnote Classic uses its familiar green, compact presentation.
- Kept ALISE credentials, reservations and payments inside the official ALISE WebView; Scoly exposes no JavaScript bridge to the page and does not read form values.
- Preserved each user's configured school portal URL, including the Ferdinand Buisson delegated ALISE address.
- Updated Android to version **5.1.2**, `versionCode 72`.

# Scoly 5.1.1

## 5.1.1 — Communication and notification reliability

- Fixed Communication synchronization being aborted by one failed discussion-detail request; list/news requests now retry with a renewed session and unavailable thread details preserve their previous cached content.
- Fixed timetable-change notifications comparing unstable PRONOTE course IDs. They now compare the old and new upcoming schedules and count additions, removals or modifications once.
- Changed the default Ferdinand Buisson cafeteria reservation destination to the direct ALISE web-parent portal.
- Added spacing between the linked-account card and synchronization error/status card.
- Reduced the Secret options safety delay from two seconds to half a second.
- Updated Android to version **5.1.1**, `versionCode 71`.

# Scoly 5.1.0

## 5.1.0 — Cafeteria access and navigation reliability

- Added a direct, configurable link to each school’s official cafeteria/ALISE reservation portal from the Menu page and the detailed cafeteria view.
- Kept meal reservations on the school portal: Scoly does not invent an undocumented ALISE API, store portal credentials or require a new paid backend.
- Preserved the existing PRONOTE/PDF menu synchronization and offline cache, including imported school menu PDFs.
- Fixed the drawer hiding Homepage before a real destination opened; submenu controls and unavailable entries no longer leave a blank page.
- Made Timetable, Homework and Student Administration explicitly switch views so their drawer navigation remains reliable.
- Updated Android to version **5.1.0**, `versionCode 70`.

# Scoly 5.0.5

## 5.0.5 — Secret options and synchronization polish

- Secret option buttons stay disabled for two seconds after the dialog opens, preventing the opening gesture from activating an option accidentally.
- Added a **Secret options** drawer tab in Scoly mode while keeping the PROnote Classic drawer unchanged.
- Added consistent inner padding around the PRONOTE sync-settings frame, rows, heading and notification controls.
- Updated Android to version **5.0.5**, `versionCode 69`.

## 5.0.4 — Timetable replacement and Homepage schedule

- Fixed the actual no-op cause: replacement completed its storage writes and then called a removed cloud-sync function, throwing before the UI could refresh or close.
- Made PDF replacement a real form submission backed directly by the existing verified, all-or-nothing timetable transaction.
- Made PRONOTE replacement close the synchronization dialog and open the newly installed week immediately; expired previews now show a visible error instead of doing nothing.
- Published the canonical timetable store before the rest of timetable UI initialization so Homepage day cards can always read the same courses as Timetable.
- Kept the previous timetable intact if replacement storage verification fails.
- Updated Android to version **5.0.4**, `versionCode 68`.

## 5.0.3 — Homepage timetable reliability

- Homepage day overview and **Your school day** now read through the same canonical timetable-store function used by the Timetable page.
- Empty or partial PRONOTE responses for an active school week are retried once and then rejected instead of erasing cached courses; genuine full holiday weeks remain valid.
- Centered the assignment completion checkmark with a fixed SVG mark inside the existing Scoly checkbox.
- Updated Android to version **5.0.3**, `versionCode 67`.

# Scoly 5.0.2

## 5.0.2 — Portable Android signing

- Bundled the existing Scoly/PROnote signing keystore inside the Android project so the source ZIP can be built on a phone or another computer without a separate PC key file.
- Replaced the hardcoded Windows keystore path with a portable project-relative path while preserving the existing signing identity and Android update compatibility.
- Updated Android to version **5.0.2**, `versionCode 66`.

# Scoly 5.0.1

## 5.0.1 — V5 reliability and interface polish

- Fixed shared Scoly Light/Dark surface and text contrast across PDF export, synchronization overlays, dialogs and narrow phone layouts while leaving PROnote Classic unchanged.
- Fixed Communication synchronization reusing an invalidated session after an empty Information & Surveys response.
- Sync All now reports failed categories clearly, preserves their cached data and safely keeps successful category results.
- Timetable replacement now erases every previous dated, repeating and imported timetable entry before installing only the newly imported or synchronized timetable, with transactional rollback if storage fails.
- Corrected Android adaptive-icon safe-zone padding without changing the supplied Scoly artwork.
- Corrected the Scoly Homepage hierarchy, dark-mode text, View all placement, assignment status/check controls, day selector and course spacing.
- Homepage and Menu cafeteria views now reuse PDF-imported meals from the existing Self cache instead of reading only PRONOTE Communication menus.
- Removed the non-PRONOTE Appearance entry from the PROnote Classic drawer while keeping Appearance available through Secret tools.
- Fixed Scoly timetable time clipping, removed the mismatched inner date-selector outline and aligned Secret tools with the active Scoly theme.
- Updated Android to version **5.0.1**, `versionCode 65`.

# Scoly 5.0.0

## 5.0.0 — PROnote becomes Scoly

- Introduced the new **Scoly** identity, app icon, launcher presentation and user-facing application name while preserving the Android package and data identifiers for seamless upgrades.
- Added the new default Scoly interface with shared coral, violet, surface, typography, spacing, shape and elevation tokens across the major existing screens.
- Added **Scoly Light**, **Scoly Dark** and **Follow system** modes with live switching that does not reload synchronized data.
- Preserved the complete V4 presentation as **PROnote Classic**, backed by the same navigation, synchronization, cache and page logic.
- Redesigned the Homepage around next course, timetable changes, upcoming homework, latest grades, unread Communication and cafeteria information using existing offline stores and deep links.
- Added a one-time upgrade introduction for existing users; new installations start in Scoly without the migration prompt.
- Preserved activation, linked PRONOTE accounts, cached/custom data, settings, offline mode, background synchronization, updater and notifications.
- Updated Android to version **5.0.0**, `versionCode 64`.

# PRONOTE 4.4.2

## 4.4.2 — Final V4 synchronization polish

- Added pull-to-refresh to Homepage, Homework, Grades and Communication using the existing serialized synchronization pipeline.
- Added consistent last-successful-sync information, category progress messages and direct Retry actions while keeping cached content visible.
- Grade, timetable and homework notification taps now open their relevant screen or date, including from a closed app.
- Grouped related Android grade and timetable notifications without removing useful individual entries.
- Startup displays cached content immediately and starts the existing background check asynchronously when the WebView becomes idle.
- Fixed QR timetable replacement being hidden by higher-priority synchronized date entries; conflicting PRONOTE overrides are removed while custom dates remain intact.
- Fixed PRONOTE timetable replacement feedback and navigation, with cached timetable preservation if installation fails.
- Centralized the few new reusable synchronization presentation colors for later theme overrides without introducing a V5 redesign.
- Updated Android to version **4.4.2**, `versionCode 63`.

# PRONOTE 4.4.1

## 4.4.1 — Homepage fidelity fixes

- Rebuilt the Homepage proportions, typography, section spacing, date controls, timetable rows, assignment controls, pale background motifs and INDEX ÉDUCATION footer against the supplied PRONOTE screenshots.
- Removed the non-PRONOTE **Homepage** entry from the side drawer. The white house button is now the only homepage shortcut.
- Changed the yellow **Reminder** panel from an automatic assignment summary into a personal editable reminder stored only on the device.
- Added the PRONOTE-style Today/Tomorrow navigator and Week A/B label to the homepage timetable preview.
- Homepage assignments now include completion state, the **I finished** checkbox and deposit action when available.
- Preserved the 4.4.0 launch update prompt, serialized background refresh and course/new-grade notifications.
- Updated Android to version **4.4.1**, `versionCode 62`.

# PRONOTE 4.4.0

## 4.4.0 — Homepage, background alerts and update prompt

- Added the PRONOTE-style Homepage from the supplied mobile recording, with the reminder banner, school portal card, upcoming assignments, today's timetable, latest grades, correspondence notebook and agenda.
- Homepage cards use the existing offline caches and link to their full screens; no duplicate data store or hardcoded school results were introduced.
- Added a quiet launch-time update check. The update dialog opens automatically only when GitHub advertises a newer version/build; offline failures stay in debug logs and never interrupt launch.
- Added periodic timetable and grade checks every 15 minutes while the app process is active, plus immediate checks after resume and reconnection.
- Background checks reuse the existing serialized renewable-session pipeline, retry/backoff behavior and transactional cache installation, preventing duplicate or competing sync sessions.
- Added stable change baselines: the first successful check is silent, later checks notify only for a real course payload difference or a previously unseen grade ID.
- Added Android notifications and an in-app notification count for course changes and new grades, with a dedicated notification channel and a user-facing on/off setting.
- Background timetable checks always target the current school week rather than whichever historical/future date is open in the timetable UI.
- Updated Android to version **4.4.0**, `versionCode 61`.

# PRONOTE 4.3.0

## 4.3.0 — Performance, synchronization reliability and QoL

- Moved PRONOTE HTTP requests and cafeteria PDF downloads off the WebView thread, preventing socket waits from freezing the interface.
- Serialized all renewable-session use across manual sync, automatic sync, Self, discussion actions and read-status updates so one operation cannot invalidate another operation's temporary session.
- Added up to two automatic retries with short backoff for connection aborts, resets and timeouts. Retries renew the session and repeat only the failed category, not work that already succeeded.
- Replaced raw socket errors with a clear offline-safe message while retaining the technical exception in Android/JavaScript debug logs.
- Automatic synchronization now refreshes every enabled category in one coordinated run instead of opening a separate competing session per category.
- Timetable synchronization now validates the selected civil date, falls back safely when the UI selection is malformed, uses local school dates without UTC day shifts, and clamps requests to PRONOTE's reported school-calendar boundaries.
- Invalid or partial timetable payloads are rejected before storage changes. An empty but valid school week remains valid.
- Timetable, homework, grades and Student Administration writes are staged before replacing their offline cache, preserving the last successful data if validation or device storage fails.
- Communication migration data is removed only after the new cache has been written and verified.
- Hidden Homework, Grades, Student Administration, Communication and Self screens no longer rebuild their full UI during startup or background synchronization.
- Communication renders only the currently visible section instead of rebuilding discussions, Information & Surveys, Agenda and Menu together.
- Optimized grade grouping to avoid repeatedly scanning the full grade list for every subject.
- Long Communication synchronization yields periodically while mapping discussion threads so touch/animation work stays responsive.
- Restored normal WebView asset caching for faster startup.
- Updated Android to version **4.3.0**, `versionCode 60`.

# PRONOTE 4.2.1

## 4.2.1 — Synchronization fixes

- Homework synchronization now deletes every existing homework entry before installing the current PRONOTE list, eliminating accumulated duplicates and obsolete local entries.
- Replaced the Information & Surveys reader with Pawnote's direct News request used by Papillon; removed the incorrect resource switching and Presence-page navigation that could return a false empty list.
- Information and survey payloads are both mapped explicitly, including questions, response choices, text, categories, authors and attachments.
- Replaced cafeteria resource probing with Pawnote's direct weekly Menu request used by Papillon.
- Added one fresh authenticated retry when PRONOTE unexpectedly returns an empty News or Menu response.
- Updated Android to version **4.2.1**, `versionCode 59`.
- The Self cafeteria dialog now scrolls vertically on phone screens, so every meal, the menu source, and the refresh controls remain reachable.
- Self now prefers PRONOTE menus, then falls back to a configurable public school menu page or PDF.
- Added a built-in fallback for Lycée Polyvalent Ferdinand Buisson and parses its weekly PDF into dated **Lunch** and **Night meal** tabs.
- Cafeteria PDFs are parsed locally on the phone; their contents are never uploaded.
- Removed all timetable, homework and profile uploads from the licence API and added a migration that permanently drops `public.license_assignments`.
- Fixed relinking so it clears only PRONOTE/ENT cookies instead of erasing the app's entire local storage.
- Mirrored the verified licence state and student name/photo into Android native storage so they survive phone restarts and WebView storage recovery.
- Temporary licence-server failures no longer erase a previously verified key; only a definitive revocation or invalid-activation response can remove it.

## 4.2.0 — Self

- Added **Self** to Secret Tools with Monday–Friday cafeteria menus from the linked PRONOTE/ENT session.
- Added week navigation, separate lunch/dinner sections and offline cafeteria-menu storage.
- Cafeteria synchronization checks every eligible student resource instead of depending on the resource active after login.
- Rebuilt Communication installation as an explicit, verified cache transaction.
- Information & Surveys are deduplicated, tracked explicitly and read back from storage; the app no longer reports success if detected items were not actually saved.
- If long discussion histories approach Android WebView’s storage limit, older message bodies are compacted before retrying so Information & Surveys still import successfully.
- Reset the Information & Surveys unread-only filter after an import so newly installed read items remain visible.
- Homework synchronization now removes the previous PRONOTE layer before importing the current remote list.
- Migrates and removes legacy synchronized homework entries that lacked a source marker, preventing repeated imports from creating duplicates.
- Preserves genuinely custom homework while deduplicating the new PRONOTE set by its remote identifier.
- Updated Android to version **4.2.0**, `versionCode 56`.
- Replaced the Notebook’s placeholder missed-hours and tardiness symbols with the supplied PRONOTE-style clock and running-student icons.

## 4.1.0 — Student Administration

- Added direct Student Administration synchronization through the linked PRONOTE session.
- Added independent one-time and automatic synchronization controls for Student Administration.
- Added the real PRONOTE-style Notebook overview and detail pages for absences, tardiness, punishments, observations and precautionary measures.
- Added justified-state, reason, duration, subject and date details when supplied by the school.
- Added downloadable documents attached to punishments and precautionary measures.
- Added Student Administration to **Sync all once**, last-sync reporting and the animated drawer navigation.
- Completed the English and French interface for the new pages.
- Rebuilt the notification panel to match the supplied full-height PRONOTE overlay instead of the incorrect compressed bottom sheet.
- Fixed Communication synchronization so Information & Surveys establishes presence, checks every eligible student resource, and retries false empty responses before discussion threads are downloaded.
- Enabling any automatic synchronization switch now performs its first synchronization immediately instead of waiting for a later app launch or timer.
- Updated the Android release to version **4.1.0**, `versionCode 55`.

## 4.0.0 Stable

- Rebuilt Communication to closely match the supplied PRONOTE recording.
- Added the complete Communication navigation: Discussions, Information & Surveys, My meetings, Agenda and Menu.
- Added discussion search, unread and open/closed filters, offline thread access and downloadable attachments.
- Added recipient lookup and new-discussion sending to teachers and other authorized school personnel.
- Added synchronized Information & Surveys with search, unread state, detail pages and attachments.
- Added the school-holiday Agenda and synchronized cafeteria menus.
- Added the PRONOTE-style notification panel and empty states.
- Rebuilt Discussions and Information & Surveys to closely follow the real PRONOTE mobile list and thread layouts.
- Removed the unwanted 20:00–07:00 message-reception banner from every Communication page.
- Replaced the fixed notification number with the real combined unread Communication count.
- Opening a discussion or information item now marks it read locally and on PRONOTE.
- Strengthened offline mode: the first key activation still requires internet, but a previously verified installation can subsequently open offline.
- Added automatic key revalidation on connected launches and whenever connectivity returns.
- Finished and polished the English/French translations across synchronization, grades and Communication.
- Kept synchronized categories read-only while their automatic synchronization is enabled.
- Released the final Android V4 build as version **4.0.0**, `versionCode 51`.

## Preview 6

- Added real PRONOTE message synchronization.
- Added the first functional Communication page and its drawer navigation.
- Added synchronized teacher discussions, message threads, dates and unread states.
- Added offline caching for previously synchronized conversations.
- Added support for viewing and downloading files attached to messages.
- Added the animated drawer expansion used by sections such as Homework notebooks and Communication.

## Preview 5

- Added real PRONOTE grade synchronization.
- Added a complete Grades area with My grades, Gradebook, Report card, Class's report card and Old report cards.
- Added grading periods, subject averages, class averages, marks, coefficients and comments.
- Added downloadable assessment and correction files when supplied by PRONOTE.
- Reworked the grade pages to match the supplied mobile PRONOTE references.
- Added the PRONOTE-style period menu, which remains accessible even when periods contain no grades.
- Added the supplied school-box illustration and polished empty-period screens.

## Preview 4

- Added real PRONOTE homework synchronization.
- Added independent one-time and automatic homework synchronization settings.
- Synchronized subjects, due dates, completion state, instructions and downloadable homework files.
- Normalized PRONOTE HTML homework text so tags such as `<div>` no longer appear in assignments.
- Added direct attachment downloading from synchronized homework.
- Automatic homework synchronization now hides the built-in demonstration homework and restores it when synchronization is disabled.
- Improved account linking through the school's normal PRONOTE/ENT sign-in flow.
- Fixed relinking so logging out and linking again restarts the ENT login instead of falling back to an unwanted PRONOTE login page.
- Stored renewable PRONOTE sessions securely using Android Keystore without saving the account password.

## Preview 3

- Added automatic timetable synchronization using Android background work.
- Added an independent timetable auto-sync switch, disabled by default.
- Added periodic refreshes while preserving the last successfully synchronized timetable for offline use.
- Made synchronized timetable data read-only while automatic synchronization is enabled.
- Added account-session renewal for background synchronization.

## Preview 2

- Added one-time timetable synchronization from a linked PRONOTE account.
- Synchronized courses, teachers, rooms, groups, cancellations and exceptional timetable changes.
- Added a timetable preview and overwrite warning before installing synchronized data.
- Added automatic Lunch and No course gaps while ensuring Wednesday never receives an artificial lunch period.
- Added gray styling for classes that already happened on the current day.
- Kept PDF import and timetable QR transfer available as optional alternatives.

## Preview 1

- Added the Synchronization section to the secret settings tab.
- Added optional PRONOTE account linking; the app remains fully usable without a real PRONOTE account.
- Added the foundation for direct synchronization using Pawnote LTS as an independent connector without copying Papillon application code.
- Added separate one-time and automatic switches for timetable, homework, grades and Communication, all disabled by default.
- Added overwrite warnings explaining that synchronized categories replace their custom equivalents.
- Added encrypted renewable-session storage and account unlinking controls.
- Added the first synchronization status, last-update and error displays.
