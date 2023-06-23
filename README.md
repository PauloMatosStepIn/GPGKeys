### GPG Key : Proof of Concept to **Verified Commits on GitHub**

ChckList to create a repo with implementation of Verified Commits

We will make use of **GPG Keys**

The following commands are executed on Windows **GitBash** Console

**Help on GPG command:**

```
gpg --help
```

**List your local GPG Keys:**

```
gpg --list-keys
```

**Create GPG Certificate:**

```
gpg --full-generate-key
```

**Edit GPG Certificate:**

```
gpg --edit-key YourEmail@mail.com
	list
	key 1
	expire
	save
```

Export PUB Key to clipboard:

**to console:**

```
gpg --export --armor YourEmail@mail.com
```

**to clipboard:**

```
gpg --export --armor YourEmail@mail.com | clip
```

**to file:**

```
gpg --export --armor --output YourName.gpg.pub YourEmail@mail.com
```

**Add GPG Key to GitHub:**

```
GitHub -> Settings -> SSH and GPG Keys -> New GPG Key
(paste to key field)
```

**search someone else key abroad**

```
gpg --search-keys CollaboratorEmail@mail.com
```

**delete someone else key locally**

```
gpg --delete-keys CollaboratorEmail@mail.com
```

**get your GPG Key Id**

```
gpg --list-keys --keyid-format LONG YourEmail@mail.com
```

**send GPG Key to external key server to share among others**

```
gpg --send-keys <KeyId>
```

**import someone else GPG Pub Key**

```
gpg import <exported file>
(gpg --export --armor --output YourName.gpg.pub YourEmail@mail.com)
```

**Require Signed Commits on GitHib**

```
GitHub -> main page of the repository -> Setting -> Branches -> Branch
Choose main branch  & Protection Rules Require Signed Commits & Save
```

**Edit Configuration** code ~/.gitconfig

```
...
[user]
  name = YourDisplayName
  email = YourEmail@mail.com
  signingkey = YourEmail@mail.com
[commit]
  gpgsign = true
[tag]
  gpgSign = true [safe]
...

```

### Documentation and References used to elaborate this page:

PROCEDURE EXPLAINED : Signing and Verifying Git Commits on the Command Line and GitHub
https://www.youtube.com/watch?v=4166ExAnxmo

PROCEDURE EXPLAINED : Creating and Managing a GPG Key Pair
https://www.youtube.com/watch?v=1vVIpIvboSg

DOCUMENTATION : Practical Introduction to GNU Privacy Guard in Windows
https://www.glump.net/howto/cryptography/practical-introduction-to-gnu-privacy-guard-in-windows

OFFICIAL SITE : GNU Privacy Guard 
https://gnupg.org/index.html

Additional Resources in this Area
https://www.youtube.com/@NickJanetakis/videos

