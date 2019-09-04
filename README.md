Syberia Project
====================

How to Build?
-------------

To initialize your local repository, use a 
command like this:

```bash
  repo init -u https://github.com/syberia-project/manifest.git -b 10.0
```
  
Then to sync up:
----------------

```bash
  repo sync -c -jx --force-sync --no-clone-bundle --no-tags
```

   . build/envsetup.sh
       brunch <device_name>

Submitting Patches
------------------
Our ROM is open source, and patches are always welcome!
You can send patches by using these commands:

    cd <project>
    <make edits>
    git add -A
    git commit -m "commit message"
    git push ssh://<username>@gerrit.syberiaos.com:29418/syberia-project/<project> HEAD:refs/for/10.0

Register at <gerrit.syberiaos.com> and use the username that you registered there in the above command

Commit your patches in a single commit. Squash multiple commit using this command: git rebase -i HEAD~<# of commits>

If you are going to make extra additions, just repeat steps (Don't start a new patch), but instead of git commit -m
use git commit --amend. Gerrit will recognize it as a new patchset.

To view the status of your and others patches, visit [Syberia Project Code Review](https://gerrit.syberiaos.com)

Maintaining Authorship
----------------------
Maintaining authorship is a very important aspect of working with Open Source code. If you wish to submit a patch/fix
from anywhere else (another ROM, project, etc.), it is imperative that you maintain the ownership of the person whose
work you are seeking to include. Doing so will ensure that credit is given where it is deserved, and the [prinicples of open source](http://opensource.org/docs/osd)
are upheld. Your contribution to the project will still be recognized as you will forever be listed as the committer.

If you manually cherry pick a patch/fix then you will need to add the original author prior to pushing to our [gerrit](https://gerrit.syberiaos.com).
This is a very easy task to perform, and is usually done after you commit a patch/fix locally. This is accomplished
after you type in `git commit -a` , type in the commit message and save. You would then do the following:

```bash
git commit --amend --author "Author <email@address.com>"
```

So it should look like this once you get all of the author's information

```bash
git commit --amend --author "Spencer McGillicuddy <spencer.the.bestest@gmail.com>"
```

Alternatively, adding as part of the original `git commit` message is preferred and done like the following:

```bash
git commit --author="Author <email@address.com>" -m "[commit message]"
```

This saves time, and when part of your normal routine, prevents the infamous "ermahgerd I forgot to add authorship -
let me fix it because I was found out!" message.