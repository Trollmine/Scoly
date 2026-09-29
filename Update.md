# Scoly 6.0.20

## 6.0.20 — Communication and Information repair

- Fixed Information & Surveys being opened and immediately hidden by the V6 navigation layer.
- Aligned PRONOTE news synchronization with Papillon's single-request Pawnote flow and hardened optional survey/attachment fields.
- Added an independent Information & Surveys diagnostic status so a Discussions success can no longer hide its sync failure.
- Separated cafeteria refresh failures from Communication diagnostics, preserved saved menus after a failed refresh and stopped false cafeteria timestamps.
- Successful refreshes now clear the matching recovered diagnostic error.

# Scoly 6.0.19

## 6.0.19 — V6 cached-page scroll repair

- Fixed short V6 tabs inheriting the vertical scroll range of taller off-screen cached tabs.
- Cached destinations remain rendered for smooth horizontal swiping, but are now clipped to the active page and can no longer create a large empty area below Homework, Grades or other shorter pages.

# Scoly 6.0.18

## 6.0.18 — V6 scroll bounds and Paid access

- Removed the duplicated V6 bottom spacer that let shorter tabs scroll into empty space.
- Preserved each tab's useful scroll position while clamping it to the selected page's real height after a swipe or tab change.
- Moved the Scoly V6 interface entitlement from Level 3 Insider to Level 2 Paid, including safe cached-claim migration and authoritative license API mapping.

# Scoly 6.0.17

## 6.0.17 — Legacy isolation repair

- Fixed the blank Scoly Legacy Homepage caused by the hidden V6 cache warmer continuing to change page visibility.
- V6 cache warming, invalidation, paging, resume handling and idle work now stop completely outside the V6 interface.
- Switching from V6 to Legacy cancels pending animation/idle work, removes every pager transform and restores the current page through its existing Legacy opener.
- PROnote Classic remains independent and is no longer touched by V6 cleanup or page restoration.

# Scoly 6.0.16

## 6.0.16 — V6 navigation rollback and layer reset

- Removed the 6.0.15 drawer transaction that could leave whole pages shrunken, translated or scattered across the screen.
- Drawer choices now use one explicit V6 route path for primary tabs and a separate clean handoff for secondary pages.
- Interrupted swipes now clear every pager class, inline transform, absolute position and temporary compositor state before another page opens.
- Added a defensive normal-flow reset so a stale Android WebView frame cannot keep carousel geometry after navigation.

# Scoly 6.0.15

## 6.0.15 — Deterministic V6 routing

- Replaced the global drawer click interceptor with an explicit route transaction that runs exactly once per page selection and never on the nested legacy button or Close action.
- Cancelled pending cache frames before navigation and validate the expected visible route before any delayed page parking can run.
- Audited every Homepage, Timetable, Homework, Calendar, Grades, My School Day, Todo, Student Administration, Communication and Insights opener so Search/Insights cannot remain stacked over another page.
- Preserved the Android resume repaint and safe cached-page z-order from 6.0.14.

# Scoly 6.0.14

## 6.0.14 — V6 layer and resume reliability

- Drawer destinations now dismantle transformed swipe/cache layers before their existing page opener runs.
- Normal pages always paint above inactive cached tabs, preventing an old swipable page from covering My School Day, Calendar, Timetable or More destinations.
- Interrupted gestures and settling animations are finalized when Scoly is backgrounded.
- Android now restores the WebView and explicitly rebuilds/repaints V6 navigation when the app resumes, fixing the touch-to-remove blank screen.

# Scoly 6.0.13

## 6.0.13 — Drawer-to-tab cache repair

- Fixed Calendar sometimes displaying the previously selected Grades page after opening it from the drawer.
- Fixed Homework and Timetable becoming empty after drawer navigation.
- Drawer handlers can now reclaim a previously cached tab safely before the V6 navigation observer parks pages again.

# Scoly 6.0.12

## 6.0.12 — V6 navigation audit & Insider access

- Fixed cached Homepage layers covering Calendar, My School Day, Grades, Insights, Communication and other drawer destinations.
- Horizontal paging now starts only after a real swipe, while taps and vertical scrolling remain responsive.
- Calendar and Communication are rendered before entering the cached page strip, and interrupted navigation is cleaned up safely.
- Scoly V6 is now a Level 3 Insider interface with online entitlement verification; Scoly Legacy remains the safe fallback.

# Scoly 6.0.11

## 6.0.11 — Homepage theme repair

- Reverted the legacy Homepage style promotion that incorrectly forced white V4 surfaces into dark V6 palettes.
- Partial swipes now temporarily reuse the real Homepage mode, producing the same layout as the settled page without overriding V6 colors.
- Kept the corrected palette-colored backdrop behind the rounded V6 header.

# Scoly 6.0.10

## 6.0.10 — Seamless Homepage swipe

- Removed the light legacy backdrop leaking around and underneath the rounded V6 header.
- Applied the remaining V4 Homepage presentation rules consistently to cached, partially sliding and settled Homepage states.
- Eliminated the final spacing and geometry jump at the end of a Homepage swipe.

# Scoly 6.0.9

## 6.0.9 — Correct partial swipes

- Fixed the Homepage losing its V6 card, button and spacing styles while only partly visible during a swipe.
- Cached and incoming Homepage layers now carry their complete page-local presentation before the tab snap finishes.
- The shared header title now follows the visually dominant tab together with the bottom-navigation selection.

# Scoly 6.0.8

## 6.0.8 — Complete swipe pages

- Fixed the remaining blank-page swipe by preventing the old global Homepage mode from hiding V6's cached and incoming Homepage.
- Cached page contents now remain visible for the complete finger-following transition, before the destination becomes active.
- Removed timetable PDF export and PDF timetable import from the V6 interface; Scoly Legacy keeps its existing PDF tools.

# Scoly 6.0.7

## 6.0.7 — Always-painted tab cache

- Fixed cached Homework and other tabs occasionally sliding in as an empty background.
- Cached primary pages now stay mounted just outside the viewport instead of becoming hidden after every snap.
- Removed deferred off-screen painting so previously rendered cards remain visible throughout repeated swipes.
- Preserved per-tab content, state and vertical scroll positions without re-rendering during navigation.

# Scoly 6.0.6

## 6.0.6 — Persistent tab cache

- Primary V6 tabs now keep their rendered DOM instead of rebuilding when a swipe finishes.
- Each tab remembers its own vertical scroll position and previews that exact position while sliding into view.
- Cached pages are warmed progressively in the background so their content is already visible during a swipe.
- Data updates invalidate and refresh only the affected cached pages; ordinary navigation performs no content render.

# Scoly 6.0.5

## 6.0.5 — Instant swipe start

- Removed synchronous route rendering from the beginning of every swipe.
- Cached bottom-navigation geometry so finger movement no longer triggers forced layout measurements.
- Avoided measuring every hidden page and let off-screen pager pages skip unnecessary rendering work.
- Prepared the lightweight pager layers on touch-down, before the first visible finger movement.

# Scoly 6.0.4

## 6.0.4 — Continuous tab pager

- Replaced queued one-page swipes with one continuous horizontal pager whose tab positions act as snap points.
- Pages and bottom-navigation selection now follow the finger from the same fractional position.
- Removed the animation lock and timed swipe suppression, allowing immediate direction changes during dragging or settling.
- Added velocity-aware snapping and multi-tab swipes without sacrificing normal vertical scrolling or button taps.

# Scoly 6.0.3

## 6.0.3 — Simpler Settings

- Reduced Settings from five tabs to three: Appearance, Preferences, and Access & support.
- Grouped Notifications with Personalization, and My Scoly Access with Diagnostics.
- Preserved existing direct routes to School Year Progress and Diagnostics, including automatic scrolling to the requested section.
- Made all three tabs fit cleanly without a second horizontally scrolling navigation bar.

# Scoly 6.0.2

## 6.0.2 — Navigation reliability

- Bottom navigation now resynchronizes after every drawer destination, including a proper More state for secondary pages.
- Serialized page transitions prevent rapid swipes or taps from creating overlapping, blinking layers.
- Quick consecutive swipe steps are buffered instead of ignored, so left-then-right reliably performs both movements.
- Reversing direction inside one unfinished gesture cancels safely instead of opening the wrong tab.
- Fixed Scoly Colors radio-button padding and alignment across the two-column palette grid.

# Scoly 6.0.1

## 6.0.1 — V6 touch & palette polish

- Made the whole page a high-priority horizontal swipe surface, including Calendar day buttons, with faster finger tracking and accidental-tap suppression.
- Improved bottom-tab press feedback and shortened directional transitions.
- Fixed the V6 drawer and scrim so the sticky header can no longer overlap the menu.
- Expanded every palette into a complete Light/Dark color system covering backgrounds, surfaces, outlines, shadows, decorative colors and overlays.
- Removed remaining palette-dependent purple shadows and drawer accents while preserving intentional category and access-level identities.

# Scoly 6.0.0

## 6.0.0 — The New Scoly

- Added the V6 bottom navigation shell with finger-following horizontal swipes and matching directional tab transitions.
- Added safe V6 / Scoly Legacy switching while keeping the same screens, repositories, sync, licensing and offline data.
- Added eight centralized Scoly palettes with Light, Dark and System modes; PROnote Classic remains available separately.
- Added two locally configurable V6 shortcuts with duplicate protection.
- Improved French dynamic dates, locale-aware formatting and added a development translation audit API.
- Preserved existing deep links, Android back handling, accessibility scaling and every V5 feature.

## 5.9.5 — Access management & safe diagnostics

- Added a clearer My Scoly Access summary with level, included capabilities, license type, status, expiration and verification state.
- Improved invalid, expired, revoked, offline and recovery-safe license handling without displaying activation secrets.
- Added share-safe Scoly Diagnostics for app/device, connections, module sync timestamps and error codes, notification/background status, and cache health.
- Added copy, text export and error-history clearing; clearing diagnostics never removes school data or settings.

# Scoly 5.9.4

## 5.9.4 — Admin level selector polish

- Removed the awkward decorative frame surrounding the Admin access-level selector.
- The selector itself now changes identity with the chosen tier: neutral Free, purple Paid, or pink-purple Insider.
- Applied the same behavior to key generation and License Details.

# Scoly 5.9.3

## 5.9.3 — Consistent Insider identity

- Beta now uses the exact same smooth pink-to-purple Level 3 frame as Admin Panel, including while online verification is pending.
- Removed the striped locked border and duplicate “Level 3” suffix; the Insider badge and explanatory text remain clear.

# Scoly 5.9.2

## 5.9.2 — Verified premium access & clearer identities

- Level 2 and Level 3 capabilities now require a successful online license verification in the current app session; cached school data and Level 1 remain available offline.
- Paid and Insider features now use full-card gradients instead of relying on small badges alone.
- Admin Panel is now a named Level 3 Insider entitlement with matching drawer styling and online verification before opening.
- Key generation and License Details both expose clearly styled Level 1/2/3 selectors; changing a level remains separate from duration and takes effect at the app's next verification.

# Scoly 5.9.1

## 5.9.1 — Paid/Insider identity & Admin access

- Made PROnote Classic a named Level 2 Paid entitlement without hardcoding a numeric-level check into Appearance.
- Added a clear purple Paid diamond and outline to Level 2 features.
- Added a distinct pink-purple gradient Insider star and border to Level 3 features such as the Beta update channel.
- Level 1 users selecting PROnote Classic receive the shared access explanation; losing the entitlement safely returns the interface to Scoly.
- Added Admin Panel under More → App & account, opening the hosted Cloudflare dashboard while retaining its server-side Google administrator check.

# Scoly 5.9.0

## 5.9.0 — Access Levels & V5 Finale

- Added independent Level 1 Free, Level 2 Paid and Level 3 Insider access, resolved through a centralized named-entitlement map.
- Added a safe database migration that preserves every existing activation, duration and expiration while assigning pre-5.9 keys to Level 2 Paid.
- Activation, verification, Google linking and recovery now return server-authoritative access claims; the last validated claim remains available offline.
- Extended Scoly Admin with level selection, level filters, level editing, clear badges and optional entitlement overrides without coupling access to duration.
- Added an Access page in Settings with the validated tier, separate duration information and Stable/Beta channel controls.
- Added an Insider-only Beta channel to the existing updater; online use revalidates entitlement and loss of Insider access returns safely to Stable.
- Added explicit Stable/Beta build and channel labels, French/English copy, accessible locked-option explanations and matching Scoly theme styling.
- Existing Scoly features remain unlocked until the permanent feature split is deliberately configured through named entitlements.

# Scoly 5.8.2

## 5.8.2 — Current-week insights

- Workload and class-time totals, distributions and charts now use only the current Monday–Sunday week.
- Removed cache-dependent “per saved week,” saved-range and busiest-saved-week statistics.
- Replaced them with actual current-week item counts, class hours, class counts, average class duration and daily breakdowns.
- Preserved historical grading-period trends, which remain meaningful for academic comparisons.

# Scoly 5.8.1

## 5.8.1 — Insights clarity

- Replaced unexplained normalized chart numbers with actual grades, item counts and class hours.
- Added concise explanations for performance, workload, subject distribution and weekly class-time charts.
- Subject distribution now shows both saved hours and the real share of total saved class time.
- Long subject names wrap above their bars on narrow screens instead of overlapping them.

# Scoly 5.8.0

## 5.8.0 — Insights & Goals

- Added an offline Insights dashboard for official/estimated grade trends, workload, busiest saved days and weeks, homework completion when known, and saved class-time distribution.
- Added local subject and period grade goals with edit/delete controls and clearly labelled current or estimated progress.
- Connected Grade Simulator scenarios to goals as estimates without changing or predicting official PRONOTE averages.
- Calculations reuse existing cached data, grade scales, coefficients and exclusion rules; missing dates, invalid durations and cancelled classes are not invented or counted.
- Added French/English copy and Scoly Light/Dark plus PROnote Classic-compatible navigation.

# Scoly 5.7.3

## 5.7.3 — Progress widget and Homepage fix

- Added a resizable School Year Progress Android widget with percentage, progress bar, completed/remaining days, milestone and current-period progress.
- The widget uses the existing offline progress dates and preferences, refreshes after saved data changes and recalculates daily without starting another sync system.
- Tapping the widget opens Settings directly at School Year Progress.
- Fixed disabling Quick Shortcuts so both Communication and Cafeteria disappear from the Homepage.

# Scoly 5.7.2

## 5.7.2 — Settings navigation polish

- The School Year Progress card's Edit button now opens Personalization directly at the relevant controls.
- Settings automatically scrolls the active tab into the best visible position, including the far-right Personalization tab.
- Preserved the drag ordering, centered switches and card-spacing fixes from 5.7.1.

# Scoly 5.7.1

## 5.7.1 — Your Scoly polish

- Replaced the Homepage editor's arrow buttons with press-and-drag ordering from the three-line handle.
- Added smooth automatic scrolling when a dragged card reaches the top or bottom of the editor.
- Centered switch thumbs consistently and moved the School Year Progress Edit button into a properly padded header layout.
- Updated French/English accessibility labels and Android release metadata.

# Scoly 5.7.0

## 5.7.0 — Your Scoly

- Added a local Homepage editor to reorder, hide, restore, and reset cards without changing their existing actions.
- Added comfortable/compact timetable density and a preferred opening page under Settings → Personalization.
- Added the customizable School Year Progress card with completed/remaining days, milestones, reliable grading-period progress, editable dates, and combined weekend/holiday counting controls.
- Progress reuses cached PRONOTE grading periods and agenda holiday ranges, works offline, and clearly reports missing date information instead of guessing.
- Added French/English support and matching Scoly Light, Dark, and PROnote Classic presentation.

# Scoly 5.6.0

## 5.6.0 — Find Everything

- Added one fast, offline global search across classes, homework, assessments, discussions, Information & Surveys, personal todos/events, Things to Bring, and calendar items.
- Added grouped results, quick category filters, accent-insensitive matching, local recent searches, and direct navigation to existing item screens.
- Search reads the existing synchronized/local stores in memory and never starts a PRONOTE request.
- Added complete French/English presentation for Scoly Light, Dark, and PROnote Classic.

# Scoly 5.5.4

## 5.5.4 — Update metadata repair

- Aligned the app, updater, release notes and Android build metadata on version **5.5.4**, `versionCode 109`.
- The update checker now treats `version.json` as authoritative and safely hides stale release notes instead of displaying a metadata-mismatch error.
- Includes the widget previews and centralized, properly padded notification settings from 5.5.2–5.5.3.

# Scoly 5.5.3

## 5.5.3 — Notification settings polish

- Centralized persistent course, course/grade and cafeteria reservation notification controls under Settings → Notifications.
- Improved spacing and padding for notification-setting cards.

# Scoly 5.5.2

## 5.5.2 — Widget previews and Settings

- Added distinct launcher previews and localized names for all three widgets.
- Moved the persistent Next Course notification control out of Appearance and into Settings → Notifications.

# Scoly 5.5.1

## 5.5.1 — Android build fix

- Corrected the Next Course notification and widget alarm ID to an integer.
- Updated Android to version **5.5.1**, `versionCode 106`.

# Scoly 5.5.0

## 5.5.0 — Scoly on Android

- Added offline Next Course, Today and Homework / My School Day home-screen widgets.
- Added an optional next-course notification in Appearance settings; it updates around course boundaries and stays off by default.
- Widgets use the existing cached timetable, homework and personal data and follow language and appearance settings.
- Updated Android to version **5.5.0**, `versionCode 105`.

# Scoly 5.4.5

## 5.4.5 — More menu dividers

- Restored the original full-width subtle line above every item in the More panel.
- Updated Android to version **5.4.5**, `versionCode 104`.

# Scoly 5.4.4

## 5.4.4 — Drawer polish

- Moved Cafeteria into the main School menu.
- Gave every item in the More panel the same subtle separator, including the first item of each group.
- Updated Android to version **5.4.4**, `versionCode 103`.

# Scoly 5.4.3

## 5.4.3 — Clearer More panel

- More now opens a separate panel with a back button and three short sections: School services, Communication, and App & account.
- Removed duplicate menu and ALISE shortcuts and placeholder report pages from Scoly’s drawer. Cafeteria actions remain accessible through Self, and the report links remain in PROnote Classic.
- Kept the six main destinations and the unchanged PROnote Classic navigation.
- Updated Android to version **5.4.3**, `versionCode 102`.

# Scoly 5.4.2

## 5.4.2 — Drawer organization

- Reorganized Scoly’s right drawer into six main destinations and a collapsed More section for secondary school pages and settings.
- My School Day replaces My Todo in the main menu; My Todo remains accessible at the top of My School Day.
- Removed nonfunctional placeholder entries and unused rail icons from the Scoly drawer. PROnote Classic keeps its existing navigation.
- Updated Android to version **5.4.2**, `versionCode 101`.

# Scoly 5.4.1

## 5.4.1 — Calendar+ polish

- Grouped each day’s classes and homework into expandable sections. Date-only homework and assessments no longer say “All day.”
- Added a legend. Dots now mean modified class, homework or PRONOTE event; ordinary classes have no dot.
- Uses the saved repeating timetable for distant days and requests the selected date from PRONOTE when online. The usual schedule is labeled until verified, and fetched dates remain available offline.
- Updated Android to version **5.4.1**, `versionCode 100`.

# Scoly 5.4.0

## 5.4.0 — Calendar+ foundation

- Added month, week and day views combining saved timetable, homework, dated assessments, PRONOTE agenda, personal Todos, school events and things to bring.
- Added local, offline personal calendar events with create, edit and delete actions. Calendar entries open their existing source screens.
- Added day indicators, subject colors, Today and period navigation in Scoly Light and Dark. PROnote Classic keeps its existing layout.
- Synchronized classes are displayed only for dates present in the saved PRONOTE timetable.
- Updated Android to version **5.4.0**, `versionCode 99`.

# Scoly 5.3.7

## 5.3.7 — Independent school menu refresh

- Refresh menus loads a configured school page or PDF directly without opening a PRONOTE session. With no source configured, it uses PRONOTE menus.
- Fixed the Android PDF response being rejected as a stale PRONOTE request. Account changes and authentication cooldowns no longer block the public menu download.
- Kept the last saved menus if the source download or PDF parsing fails.
- Updated Android to version **5.3.7**, `versionCode 98`.

# Scoly 5.3.6

## 5.3.6 — Real parent-child request scoping

- Fixed the remaining parent-account failure where the selected child appeared correctly but every PRONOTE data page rejected the request.
- Added the active child as PRONOTE's required `membre` signature on timetable, homework, Student Administration, grades, Communication and cafeteria requests.
- Applied child scoping inside the Pawnote request layer so reconnects and category retries cannot lose the selected child.
- Kept normal student-account request payloads unchanged.
- Added request-level regression coverage for every synchronized parent data category.
- Updated Android to version **5.3.6**, `versionCode 97`.

# Scoly 5.3.5

## 5.3.5 — Parent account connection repair

- Repaired parent sessions when PRONOTE changes the per-child resource IDs after renewing the saved token.
- Reconciled children by a unique name, class and school identity instead of switching silently to the first child.
- Migrated each child's cached data, selected state, photo and profile overrides to the refreshed resource ID.
- Kept child caches isolated and preserved the selected child across reconnects and app restarts.
- Refused ambiguous matches safely, without overwriting another child's synchronized data.
- Left the student-account resource selection path unchanged and added a dedicated parent regression test.
- Updated Android to version **5.3.5**, `versionCode 96`.

# Scoly 5.3.4

## 5.3.4 — Authentic grades in PROnote Classic

- Restored the compact official-style grade presentation whenever **PROnote Classic** is selected; the Grades+ dashboard remains available in Scoly Light and Dark.
- Added the familiar **Date** and **Subject** tabs, search control, subject averages, assessment rows, group averages and bottom period averages.
- Added the PRONOTE-style test-detail sheet with the student's grade, group average, highest and lowest grades, coefficient and previous/next navigation.
- Kept synchronized subject and corrected-copy attachments downloadable from the list and detail sheet.
- Added English and French labels for the complete Classic grade interface.
- Updated Android to version **5.3.4**, `versionCode 95`.

# Scoly 5.3.3

## 5.3.3 — Grade Simulator polish

- Made the Grade Simulator a collapsible Grades section that is closed whenever the Grades page opens.
- Added a rotating disclosure arrow and a badge showing the number of local simulations in the selected period.
- Reorganized the phone form into consistent Subject, Assessment, Grade, Scale and Coefficient rows.
- Moved **Reset period** into the expanded workspace, matched it to the active theme color and disabled it when there is nothing to reset.
- Preserved the separate local-only simulation store and all Grades+ calculations.
- Updated Android to version **5.3.3**, `versionCode 94`.

# Scoly 5.3.2

## 5.3.2 — Student synchronization restored

- Restored the login-first student-account flow that worked before multiple parent/child profiles were added.
- Student accounts now use the current resource returned by PRONOTE and automatically repair a stale locally saved resource ID.
- Kept strict child matching only for actual parent accounts, preventing the parent safety rule from blocking a normal student account.
- A timetable, homework, grade, Communication or cafeteria page-session expiry now reconnects and retries without falsely rejecting the whole saved account.
- Cleared the erroneous authentication pause created by affected builds once, while retaining protection for a genuinely rejected renewable login.
- Allowed linked student accounts with damaged/missing local profile metadata to rebuild that metadata during synchronization.
- Added regression coverage for student-resource repair, category-page renewal, authentication cooldown and reconnect races.
- Updated Android to version **5.3.2**, `versionCode 93`.

# Scoly 5.3.1

## 5.3.1 — Reliable PRONOTE reconnect

- Fixed the race where an automatic synchronization using the old token could fail after a successful ENT reconnect and incorrectly pause the newly linked session.
- Added session generations: old JavaScript and Android-network responses are invalidated as soon as account linking starts and can no longer overwrite new authentication state.
- Serialized the ENT, QR and direct-credential completion paths with the synchronization queue instead of discarding the website callback while another sync is busy.
- Suspended automatic synchronization throughout account linking and added a clean cancellation callback when the ENT screen is closed.
- Added regression coverage for both the authentication cooldown and the late-old-session reconnect race.
- Updated Android to version **5.3.1**, `versionCode 92`.

# Scoly 5.3.0

## 5.3.0 — Grades+

- Added a richer Grades dashboard with official and estimated averages, counted-grade totals, overall and per-subject evolution graphs, and comparisons across real historical periods.
- Added scale- and coefficient-aware estimates that ignore non-numeric, optional, bonus and zero-coefficient assessments without changing PRONOTE's official averages.
- Added subject statistics, class statistics only when supplied by PRONOTE, richer assessment details and attachment access.
- Added a fully local grade simulator with custom scales and coefficients, editing, removal, reset and estimated impact, plus a compact Grades+ homepage summary.
- Added French/English presentation across Light, Dark and PROnote Classic themes.
- Prevented rejected or expired PRONOTE sessions from triggering repeated hidden login attempts: automatic sync now pauses locally after an authentication rejection and keeps all offline data.
- Cafeteria refresh now retains cached menus and can use the configured school page/PDF fallback even while PRONOTE authentication is unavailable.
- Updated Android to version **5.3.0**, `versionCode 91`.

# Scoly 5.2.9

## 5.2.9 — Unified Scoly coral

- Replaced the old dark coral fill token with the brighter original coral across every Scoly component that uses it, including headers, action buttons, drawer accents, personal pages, unread badges and the administration dashboard.
- Updated Android to version **5.2.9**, `versionCode 90`.

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
