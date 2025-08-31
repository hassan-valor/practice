# EXTRA-CREDIT.md

## 1) Why I cloned with `--recursive`

I had to use `--recursive` when cloning because the repo has submodules. If I just did a normal `git clone`, those submodules would come in empty. Using `--recursive` made Git pull in the submodules at the right commits, so I got everything I needed for the project to build and run.

---

## 2) Why I had to set upstream for `main` but not always for the release branches

My local `main` didn’t automatically know what remote branch to track since I changed remotes around. That meant I had to manually set the upstream so it would push and pull from `myrepo/main`. But when I created branches like `v4.1.x` or `v5.1.x`, I usually based them directly on the remote branch or pushed with `-u`, and Git set the upstream automatically. That’s why `main` needed the extra step while the release branches didn’t.

---

## 3) Part 2 — why not cherry-pick commit `72a89ea32f`

That commit from `main` didn’t apply cleanly to the older branch. If I cherry-picked it, it would either cause conflicts or bring in changes that didn’t belong. Instead, I just edited the `configure.ac` file directly to make the exact same fix. This way the branch only got the one small change it needed, nothing extra.

---

## 4) Part 3 — why I had to write my own PR title and description

GitHub only auto-fills a PR title and description when there’s one clear commit to use. In Part 3 I had more than one commit in the branch, so GitHub couldn’t auto-fill a nice message. That’s why it just gave me the branch name and left the description blank, and I had to write my own title and description so the PR made sense.
