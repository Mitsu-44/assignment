# Git & GitHub Practice Homework

You've seen Git and GitHub in class. Now do the whole flow yourself: **fork, clone, branch, fix, commit, push**.

This should take about 20-30 minutes. If you get stuck, run `git status` first. It usually tells you what to do next.

---

## Steps

### 1. Fork this repository
Click the **Fork** button at the top right of this page. GitHub makes your own copy of the repo under your account.

### 2. Clone *your* fork
Copy the URL of **your** fork (it has your username in it), then run:

```bash
git clone https://github.com/<your-username>/git-practice-homework.git
cd git-practice-homework
```

> Clone your fork, not the original repo. You can't push to the original.

### 3. Create a branch
```bash
git switch -c fix/<your-name>
```

### 4. Do the tasks below
Commit after **each** task, with a clear message. Don't do everything in one commit.

### 5. Push your branch to your fork
```bash
git push -u origin fix/<your-name>
```

### 6. Open a Pull Request to the original repo
Open your fork on GitHub. You should see a **Compare & pull request** button for your branch. (If not, click **Contribute**, then **Open pull request**.)

- Make sure the **base repository** is the original repo you forked from, and the base branch is `main`.
- Set the title to `Homework: <your name>`.
- Click **Create pull request**.

That's your submission. There's no need to send a link.

---

## Tasks

### Task 1: Fill in `notes.txt`
Open `notes.txt` and fill in your name and batch. Then:

```bash
git add notes.txt
git commit -m "Add my notes"
```

### Task 2: Fix `hello.c`
`hello.c` has three problems. Find and fix all of them:

1. The greeting has a typo.
2. The name is still a placeholder. Put in your real name.
3. The two lines of output run together. They should be on separate lines.

Then stage and commit the file with a message that says what you fixed.

*Optional:* if you have a C compiler, check your fix with `gcc hello.c`, then run `./a.out` (on Windows: `a.exe`).

### Task 3: Add a `.gitignore`
Create a file named `.gitignore` that tells Git to ignore compiled programs:

```
a.out
*.exe
```

Commit it.

### Task 4: Check your work
Before pushing, run:

```bash
git status        # should say "nothing to commit, working tree clean"
git log --oneline # should show at least 3 commits of yours
```

---

## After you submit
- If GitHub says your Pull Request has **conflicts**, that's normal here. Many people are editing the same files. Just take a look at what it shows.
- If you're asked to change something, commit and push to the **same branch**. Your Pull Request updates by itself.

---

## Stuck? Common problems

- **"Permission denied" or "403" when pushing:** You cloned the original repo instead of your fork. Clone your fork's URL.
- **"Author identity unknown":** Set your name and email once with `git config --global user.name "Your Name"` and `git config --global user.email "you@example.com"`.
- **"Authentication failed":** GitHub doesn't accept your account password in the terminal. Log in with `gh auth login` or use a personal access token.
- **"src refspec ... does not match any":** You haven't made a commit yet. Run `git status`, then add and commit.
- **Not sure where you are:** Run `pwd` to see your folder and `git status` to see your repo.