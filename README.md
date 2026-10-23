# Congregation app — help page

A single public page explaining the mobile app to publishers: getting in, the
home screen, the schedule, and the documents.

One file, `index.html`, with no build step and no dependencies. Open it in a
browser to see it. The screenshots it wants are listed in
[`shots/README.md`](shots/README.md) — until they are added, each slot shows a
dashed box naming the shot that belongs there.

## Publishing it

This is deliberately **not** part of the scheduler repository. That one is
private, and GitHub Pages on a private repository needs a paid plan; making it
public to host one page would expose the whole codebase. A separate public
repository costs nothing and exposes nothing but this page.

```sh
cd Scheduler.Help
git init
git add .
git commit -m "Help page for the congregation app"
gh repo create scheduler-help --public --source=. --push   # or create it on github.com
```

Then on GitHub: **Settings → Pages → Source: deploy from a branch → `main` / root.**
A minute later it is live at:

```
https://<your-username>.github.io/scheduler-help/
```

Updating it afterwards is a commit and a push; Pages redeploys on its own.

## Linking to it

The address is public and needs no sign-in, so it can go anywhere:

- a line at the bottom of the assignment emails
- a message to the congregation
- an item on the app's own home screen, if that is wanted later

## What to keep in mind when editing

The page quotes the app's own labels in bold — **Unlock**, **Report away
dates**, **Assignments Schedule** — so that the words on the page match the
words on the screen. If a label changes in the app, change it here too, or the
instructions start sending people looking for something that is not there.

The who-sees-what table reflects how the API actually gates each download, not
how it is often described. Check it against `BuildCongregationDocuments` and
the document filtering in `Scheduler.Api/Program.cs` before changing a row.
