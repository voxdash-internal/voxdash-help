---
title: "Questionnaire Builder & AI-CATI — Feature Inventory"
date: "2026-10-24"
---

# Questionnaire Builder & AI-CATI — Feature Inventory

**For:** the Help Center author
**Source:** the `voxdash-data-provider` frontend code, checked against the stage app
(`stage-studio.voxdash.com`) on 2026-10-24.
**Purpose:** a complete list of user-facing features. Each item says which help page covers it.

The app's on-screen wording comes from the backend dictionary and can change. Where the app's
label differs from the internal name, the on-screen label is used (for example, AI-CATI
"fieldworks" are shown as **studies**).

---

## Part 1 — Questionnaire Builder

### 1.1 Questionnaire list — `Questionnaire-List`

**Summary and layout**
- Summary cards: Total questionnaires, Active/Published, Draft, Archived.
- Quick tour (Compass), a 5-slide introduction: Overview, Create, Editor, Versions, Manage.

**Table columns**
- Name: a link to the editor. A **Demo** badge marks platform sample questionnaires.
- Status: Draft, In review, Approved, Active, **Published**, **Published for AI-CATI**, Archived,
  or **Processing** (an import is still running).
- Last modified, Created.
- Questions (count).
- Data collection modes.
- Organizational access, Access type (Public, Only me, Group, User, **Over plan limit**), Public access.

**Working with the table**
- Quick search, column filters, sorting, column chooser, Clear filters.
- Expand a row to see the **inline versions panel** (View opens that version).

**Row actions**
- Duplicate, Edit, Version history, **Data project access**, Open link, Delete.
- These actions are disabled while the questionnaire is Processing or read-only, and a reason is shown.

### 1.2 Create a questionnaire — `Create-questionnaire`, `Import-Review`

**Choose a method:** Manual, or Upload (marked Beta).

**Manual: the survey-info form**
- Title is required.
- Default language must be one of the selected languages.
- At least one data-collection mode is required.
- If the questionnaire collects PII, a PII description is required; the same applies to incentives.

**Upload**
- From your device or from the VoxDash Library.
- Accepted formats: .doc, .docx, .xls, .xlsx, .pdf, .sav, .sps, .csv.
- Processing: AI processing (shows a cost and time estimate; **not available on the Free plan**)
  or standard processing.

**Import review wizard** — three steps:
1. Detect questions.
2. Identify logic (display, skip and termination rules).
3. Import summary (including quota groups).

The wizard also has an Import logic toggle, Skip, and Re-import.

**Plan limit:** when you reach your questionnaire limit, a notice with an upgrade link is shown.

### 1.3 Editor — `Editorpanel-designer` and the related pages

**Header**
- Version badge (click to rename) and an info popover.
- Generate dummy data.
- Publish button. It changes as the questionnaire moves on: Publish → Publish for AI-CATI → Create AI-CATI.

**Toolbar**
- Overview: KPIs, sections and type breakdown; clicking an item filters the canvas.
- Team, Quota, Audit log, Preview, View in VoxDash, Export.
- Versions: the versions drawer, Lock/Unlock, Save as version.

**Filters**
- Search with these filters: question type, element type (screener, quota, demographic,
  administrative, in-house randomization, interviewer or system autocode), custom tags, has logic,
  has geo map.
- Sections, Mode, Language, Screener.

**Saving and leaving**
- Autosave, with a status of Saving / Saved / Error with Retry.
- A local draft is restored after a crash.
- Leave-page guards warn while saving, after a failed save, when the JSON is invalid, or while a
  translation is running.
- Undo/redo, including Ctrl+Shift+Z.

**Limits and safeguards**
- Organization question limit: questions added over the limit are rolled back, and you can
  download a backup of them.
- Deleting a question that other logic uses asks for confirmation first.
- A Quota tag can't be removed while the question is linked in a quota group.

**Read-only banners**
- Locked, no permission, a sealed (published) version, or previewing another version.

**Canvas adorners**
- Ask AI, Missing values shortcut, Note / View note, Question preview.

**Tabs**
- Designer, Preview (with Share), Logic, JSON Editor (with the "Apply settings" prompt), Translations.

**Property-grid tabs**

| Tab | Covered in |
| --- | --- |
| General settings | `Editorpanel-designer` |
| AI Assistant | `AI-Assistant` |
| Tags | `Tags` |
| Question metadata (labels, SPSS, data type, missing values) | `Question-metadata` |
| TTS | `tts` |
| LOI | `LOI` |

**Choices grid**
- **Visible** column, exclusive / fixed-position choices.
- Other item: Other required, Read "Other" aloud.

### 1.4 Tags — `Tags`

- **Basic:** Visible, Read-only, Required, Show title, Show description.
- **Classification:** Quota, Administrative, Screener, Demographic, In-house randomization.
- **Auto code:** a taxonomy of system, interviewer and operator codes. Each code has a method, and
  some codes need a derivation setup.
- **Geo map:** pick a map, or add and preview a custom map.
- Section, Custom tags, Data collection mode, Multi-language.
- Tags set on a panel are passed down to its child questions.
- Changing a question's type resets tags the new type doesn't support.

### 1.5 Question metadata and missing values — `Question-metadata`

- **Labels:** SPSS variable and value labels, with byte counters.
- **Advanced SPSS:** format, width and decimals, set at question or questionnaire level.
- **Data type** and measurement level.
- **Missing and special values:**
  - Up to 3 slots (A, B, C), each with Code, Label and Enabled.
  - Each value shows where it comes from: Admin, Questionnaire or Question.
  - Code rules apply; Reset is available.
- **Questionnaire-level missing values:** Overwrite pushes them to all questions.

### 1.6 Translation — `Editorpanel-translation`

- Manual translation.
- **Auto-translate all / missing:** runs in the background with progress and a report. A cost
  estimate is shown, and the run is blocked if credit is insufficient.
- Add or remove languages.
- Import and export translations: CSV, TSV, TXT, XLSX, XLS, XLSM.

### 1.7 TTS and LOI — `tts`, `LOI`

**TTS**
- Voice settings, and the scope to generate for (all, page, panel, question or filtered).
- Cost estimate, progress, and a preview player.
- Custom pronunciations, using IPA or "pronounce in another language" (needs a multilingual voice).
- Voice history, with Download all (ZIP).

**LOI**
- An estimate for each data-collection mode: the VoxDash estimate, your own estimate, and timing
  per question type.
- Multipliers, average path %, and Reset.
- AI **Shorten**.

### 1.8 AI Assistant — `AI-Assistant`

- **Scope:** question, panel, section, filtered questions, or the whole questionnaire.
- **Actions:** shorten, predict type, chat, SPSS label suggestions, pronunciation scan, translate logic.
- **Readable logic:** explain or write logic.
- **Suggestions:** review mode with Accept / Reject / Dismiss, Accept all, and Undo.
- **History:** runs, progress and cost.
- **Refusals:** not in plan, no credit, version locked.

### 1.9 Preview, share and test links — `Editorpanel-preview`, `Share-and-Test-Links`

- **Share dialog:** a preview link or a test (save) link.
- General access: Restricted or Anyone with the link; a people-with-access list.
- **Start a test link:** answers go to a destination data project and survey.
- A warning appears when testing a draft, and you're asked before an existing link is replaced.

### 1.10 Logic and JSON — `Editorpanel-logic`, `Editorpanel-JSON`

- Logic tab: conditions and triggers.
- Deleting a question that logic references asks for confirmation.
- JSON editor validation, and an Apply-settings prompt for tag, missing-value and SPSS blocks.

### 1.11 Export — `Export`

**Steps:** Format → Configure → Validation → Download.

**Formats**
- Respondent PDF, Editable PDF, Annotated (PDF/DOCX), Excel data map, **Logic spec (XLSX)**,
  JSON, SPSS shell, SPSS with dummy data.
- **SPSS test responses** and **PDF test responses** need a test link that has been answered.

**Options**
- Language (required), mode, sections, question scope, include logic, value labels.
- Skip-quota / resolve choices.
- A stale-export warning.

### 1.12 Dummy data — `Dummy-Data-Generation`

- **Count:** 1–100. Also choose the mode and the data project (existing or new).
- **Survey placement:** a new survey, or replace an existing one.
- Validation runs before generation. A progress widget can be minimized.
- When it finishes: View result or Download.

### 1.13 Quotas — `Quota`

**Groups page**
- Stats cards and a groups table.
- Row actions: Edit, Validate, Export, Delete.
- **Download:** Excel or JSON.
- **Upload:** from your device or the Library, then Validate → Preview → Apply.
- Export to File Manager.

**Create group wizard:** Basics → Questions (quota-tagged only) → Configure (single or interlocked
cells, numeric bands, colour slices) → Settings.

**Group page**
- Cells in Matrix, Table or Canvas view.
- For each cell: Hard or Soft, minimum and maximum targets, match all or any, and spillover.
- Linked questions. Settings: Count each selection, prefer least-filled with max selections, total
  target.
- Validation panel. Autosave.
- Read-only on sealed or locked versions.

### 1.14 Versions — `Questionnaire-Versions`

**Version types**

| Type | Can you edit it? |
| --- | --- |
| Editable (Draft) | Yes |
| **Published** | No — sealed |
| **Published for AI-CATI** | No — sealed |

Each version can also carry the badges Active and Locked.

**Where versions appear:** the versions drawer in the editor, and the Version history page (type
filter and "Based on" lineage).

**Actions**
- Switch, Restore, Preview.
- Save as version; New version from…
- Rename, Delete (only a non-active draft), Lock/Unlock.

The Version history page has no compare feature.

### 1.15 Publish — `Publish-questionnaire`

**Preflight checks.** Warnings don't block publishing; errors do. The checks are:
- Invalid content.
- Forward references.
- Missing values.
- Screener or quota order.
- Reachability.
- Unsupported types.

**Missing-values step:** **Fill for me** assigns 999 (or 9999 if 999 clashes with an answer
code), or you can Skip. A receipt lists what was done.

**Seal warning:** a published version is sealed for good; to make changes, create a new version.

### 1.16 Audit log, Team — `Audit-Log`, `Team-and-Permissions`

**Audit log**
- Period: 7, 30, 90 or 365 days.
- Filters: activity type, people, and search.
- Logged activity covers questionnaire, version, dataset and quota changes.
- Plans without audit trails see an upgrade screen.

**Team**
- Collaborators, with permission levels from View only to Full access.

---

## Part 2 — AI-CATI (AI telephone interviewing)

A questionnaire version can be used in AI-CATI only when it is **Published for AI-CATI**.

### 2.1 Studies list — `AI-CATI-Overview`, `Studies-List`

**Layout and entry points**
- Quick tour: 4 slides.
- Ways in: New study, the "Add" menu, dashboard shortcuts, and **Create AI-CATI** in the
  Questionnaire Builder.

**Table columns**
- Study name and Study ID.
- Status: Draft, Ready to launch, Scheduled, Running, Stopped (graceful, hard or emergency), Out of
  credit, Closed (Target reached / Stopped short), Archived.
- Progress, Last dial, Last activity, Client, Questionnaire, Languages, Access.

**Row actions**
- Edit, Open, View in VoxDash, Duplicate (warns about re-calling people), Manage access.
- Restore or Delete — archived studies only.

### 2.2 Setup wizard (7 steps)

Each step opens only after the earlier ones are complete. The wizard is read-only after the first
dial, except for the settings that can still be edited while the study is stopped.

| Step | Help page | What you set |
| --- | --- | --- |
| 1 Basics | `Setup-Basics` | Name, data project (or create one), time zone, start (when I launch / scheduled), two legal attestations |
| 2 Questionnaire | `Setup-Questionnaire` | Pick a version published for AI-CATI; bind-time gate checks; interview languages; content review; routing summary |
| 3 AI interview | `Setup-AI-Interview` | AI voice and preview; read-only spoken scripts; AI interviewer profile |
| 4 Sample | `Setup-Sample` | Upload CSV/XLSX/TXT; sample type; column mapping (roles); cleaning; composition; target completes and feasibility; population size; dial-order randomization; sub-sample plans |
| 5 Screening & targets | `Setup-Screening-Targets` | Screener summary; distribution targets (reported only, not enforced) |
| 6 Calling rules | `Setup-Calling-Rules` | Calling-window grid; attempts, spacing and retry schedule; callbacks; stop rules; graceful or hard stop; ring timeout; dropped-line re-dials; maximum interview length; call recording and consent |
| 7 Cost & review | `Setup-Cost-Review` | Voice pipeline; capacity tier; maximum records in progress; cost band and breakdown; expected rates; review tiles; spend cap; approvals; Finish setup |

### 2.3 Launch and run — `Launch-and-Readiness`, `Study-Page-and-Actions`

**Launch dialog**
- Self-test call, Pre-test, Final launch, or Sub-sample.
- Readiness checks; hold card; scheduled start.
- A readiness page lists every check, each with a "Fix in step N" link.

**Study page**
- Tabs: Setup, Tests, Sub-samples, Live monitoring, Results.
- Actions depend on the status: Launch, Change start, Stop calling, Emergency stop (a reason is
  required), Resume (re-priced; you may need to accept current rates), Close, Duplicate, Restore.
- Setup tab: settings history and the questionnaire snapshot.

### 2.4 Tests and sub-samples — `Tests-Pre-tests-and-Self-tests`, `Sub-samples`

**Tests**
- Pre-test runs: statuses, run page, Stop / Resume / Close run.
- Self-test call to your own phone: live stages, End test call (soft or hard), call details.

**Sub-samples**
- Field the study in parts; one run dials at a time.
- On a Draft study you create plans; Finish setup turns them into prepared runs.
- Create dialog: distributed draw, filters, size, mix variables, shortfall policy, review and reserve.
- Run page: Overview, Monitoring, Results, Activity, Exports.

### 2.5 Monitoring, results, records — `Live-Monitoring`, `Results-and-Export`, `Sample-Records`

**Live monitoring**
- KPIs: completes, in progress, RR3, COOP1, coverage, STT confidence, cost.
- Margin of error, ramp status.
- Charts: progress, dispositions, attempts, daypart heatmap.
- Composition, quality, budget, projected finish.

**Results**
- Per call / per sample record views, with filters.
- AAPOR outcome table and rates.
- Cost reconciliation, sample accounting, targets vs achieved, downloadable reports.
- **Export:** metadata, raw data or everything; SPSS, CSV or ZIP with transcripts and recordings;
  production or a single sub-sample run.

**Sample record**
- Status and call history.
- Recordings and transcripts, answers, quality.

### 2.6 Money and limits — `Costs-Credits-and-Limits`

**How money is handled**
- The estimate is a Low / Expected / High band.
- Capacity tier multiplies the platform cost: Standard ×1.0, Fast ×1.5, Guaranteed ×2.0.
- At launch, the high estimate is held from AI credits; anything unspent is refunded.
- The spend cap is required, minimum $1, and is shared by the main launch and sub-samples.

**Hard limits**

| Setting | Limit |
| --- | --- |
| Study name | 255 characters |
| Interview length | 1–120 minutes |
| Attempts | 1–10 |
| Spacing | 1–48 hours |
| Ring timeout | 5–120 seconds |
| Dropped-line re-dials | 0–5 |
| Wait before re-dial | 1–240 minutes |
| Records in progress | 50–10,000 |
| Expected rates | 0–100% |
| Sub-sample run slots | 20 per study |
| Mix cells | 1,000 |
