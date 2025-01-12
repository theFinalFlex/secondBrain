
This guide will walk you through setting up a sync between your Obsidian notes and a private GitHub repository, so you can have version control, cloud backups, and multi-device access for your notes.

---

## **Step 1: Set Up Git and GitHub**

### 1. Install Git:
- If Git isn’t already installed, download it from [git-scm.com](https://git-scm.com/) and follow the installation instructions.
- Configure Git with your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### 2. Create a GitHub Repository:
- Log in to [GitHub](https://github.com/) and create a new repository.
- Make it **private** if you don’t want others to see your notes.
- Do not add a README, `.gitignore`, or license file during creation (this ensures a clean setup).

---

## **Step 2: Initialize Git in Your Obsidian Vault**

1. Open your Obsidian vault folder in your file explorer.
2. Open a terminal (or Git Bash) and navigate to your vault folder:

```bash
cd /path/to/your/vault
```

3. Initialize a Git repository in your vault folder:

```bash
git init
```

4. Add the GitHub repository as a remote:

```bash
git remote add origin https://github.com/yourusername/your-repo-name.git
```

---

## **Step 3: Configure a `.gitignore` File**

To avoid syncing unnecessary or system-specific files, create a `.gitignore` file in your vault folder:

1. Create a `.gitignore` file using your terminal or a text editor:

```bash
echo ".obsidian/
.DS_Store
Thumbs.db" > .gitignore
```

2. Add and commit the `.gitignore` file:

```bash
git add .gitignore
git commit -m "Add .gitignore file"
```

---

## **Step 4: Sync Your Notes**

### 1. Stage and Commit Your Notes:
- Add all your files to Git’s staging area:

```bash
git add .
```

- Commit the changes:

```bash
git commit -m "Initial commit of Obsidian notes"
```

### 2. Push to GitHub:
- Push your changes to the GitHub repository:

```bash
git branch -M main
git push -u origin main
```

---

## **Step 5: Syncing on a New Device**

To access your notes on another device:

1. Install Git and Obsidian on the new device.
2. Clone the repository:

```bash
git clone https://github.com/yourusername/your-repo-name.git
```

3. Open the cloned folder as a vault in Obsidian.

---

## **Step 6: Regularly Update Your Notes**

To keep your GitHub repository updated:

1. After making changes in Obsidian, stage and commit them:

```bash
git add .
git commit -m "Update notes"
```

2. Push the changes to GitHub:

```bash
git push
```

To pull updates from GitHub on another device:

```bash
git pull
```




