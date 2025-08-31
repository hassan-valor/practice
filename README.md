# EXTRA-CREDIT.md

## 1) Why did you have to specify the “recursive” flag when initially cloning the assignment repository? Explain in detail.

I had to use `--recursive` because the repo includes submodules. If I only did a normal `git clone`, the submodules would just be empty folders pointing at commits. By adding the recursive flag, Git also pulled in those submodules at the correct commits. That way my repo matched what the project needed to build and run.

---

## 2) Why did you have to manually set the upstream tracker for the main branch in your local repository (but potentially not the v4.1.x and v5.1.x branches)? Explain in detail.

My local `main` didn’t automatically know what remote branch to track after I changed remotes. Since `main` already existed, Git didn’t reset it on its own, so I had to manually point it to `myrepo/main`. On the other hand, when I created branches like `v4.1.x` and `v5.1.x`, I made them directly from the remote branch or pushed with `-u`. In those cases, Git set up the upstream tracking automatically, so I didn’t need to do it manually.

---

## 3) In Part 2, why didn’t we cherry pick commit 72a89ea32f from main, and instead we had you edit the configure.ac file directly? Explain in detail.

That commit from `main` wouldn’t apply cleanly to the release branch. If I tried to cherry-pick it, it could cause merge conflicts or pull in extra changes that didn’t belong. The simpler and safer option was just to edit the `configure.ac` file directly to make the one change we needed. This way the branch only got the right fix without dragging in unrelated stuff.

---

## 4) In Part 3, why did you have to write your own PR title and description for the first PR? I.e., why didn’t GitHub automatically fill in a human-readable title and description? Explain in detail.

GitHub only auto-fills a PR title and description when the branch has one clear commit it can use. In Part 3, the branch had more than one commit, so GitHub didn’t know which commit message to pick. That’s why it just left the description blank and gave me the branch name. I had to write my own title and description so the PR would explain clearly what the changes were.
