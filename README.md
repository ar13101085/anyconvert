# AnyConvert — issue tracker

**This repository holds issues only. There is no source code here.**

AnyConvert is two applications, and each has its own private GitLab
repository:

| App         | What it is                                          |
| ----------- | --------------------------------------------------- |
| Site        | The public converter — 415 conversions, 473 pages    |
| Admin panel | The control panel that edits what the site shows     |

Fixes are made and deployed from those repositories. This tracker is where
bugs and tasks are reported, discussed and signed off.

## Filing an issue

Start the title with the app it affects, so it is clear which repository the
fix belongs in:

```
[site]  Pricing page shows the annual badge on the monthly tab
[admin] Saving a route with no format silently does nothing
```

Include, when you can:

- the URL or screen, and the steps that get there
- what you expected and what actually happened
- a screenshot — for anything visual it is the fastest way to settle it
- the browser and whether it was desktop or mobile

## Labels

| Label                | Meaning                                          | Who sets it |
| -------------------- | ------------------------------------------------ | ----------- |
| `Ready_To_Fix`       | Ready to implement. This is the developer queue. | QA / client |
| `WAITING_FOR_ANSWER` | Blocked on a question asked in the issue.        | Developer   |
| `READY_TO_DEV_TEST`  | Fix is deployed and ready to test.               | Developer   |
| `DEPLOY_DONE`        | This fix is on the live site now.                | Developer   |

An issue is only picked up once it carries **`Ready_To_Fix`**. Reported but
unlabelled means it has not entered the queue yet.

## How a fix travels

1. QA or the client files the issue and labels it `Ready_To_Fix`.
2. A developer takes it, in a batch of three or four.
3. Questions are asked **as comments on the issue** — never over chat or a
   terminal — and the issue gets `WAITING_FOR_ANSWER` if the answer blocks the
   whole fix. Answer in a comment and the label comes off.
4. Fixes are deployed in batches, not one at a time.
5. After deploy the issue gets `READY_TO_DEV_TEST` + `DEPLOY_DONE`, and it is
   back with QA to confirm on the live site.

If a fix is labelled `READY_TO_DEV_TEST` and it is still wrong, reopen the
conversation on the same issue rather than filing a new one.

## Before you file: two things that are not bugs

**Signing in accepts any email and any password.** There is no backend and no
database yet. The password field is never checked, so "it let me in with the
wrong password" is expected. Everything an account shows — plan, usage,
history, invoices, API keys — is generated in your browser the moment you sign
in and stored there.

Because of that:

- a different browser, or a private window, is a different account
- signing out and back in gives you a **different** history, not the one you
  had
- nothing you do is visible to anyone else, on any other machine
- no file you drop is uploaded anywhere

**The admin panel has no login.** That is the current state, not a security
hole someone forgot to report.

Real conversion, real accounts and real storage arrive with the backend. Until
then, issues about *how those screens look and behave* are useful; issues about
the numbers not being real are already known.
