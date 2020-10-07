git-remote-gcrypt example
---

This repo contains an example "remote" generated by pushing via
[git-remote-gcrypt](https://spwhitton.name/tech/code/git-remote-gcrypt/).

Look at the initial commit
[e2f4d5726fc3ef54697ac10aa65b51a37c063f3a](https://github.com/GenerousLabs/gcrypt-example/commit/e2f4d5726fc3ef54697ac10aa65b51a37c063f3a)
to see what git-remote-gcrypt does. Every time the repo is updated, it force
pushes a new commit that replaces this commit. So there's always a single
"initial commit" that contains the encrypted data.

To make it clearer, I decrypted the `91bd...` manifest file (with the
extension `.txt`). Then I decrypted the packfile `8134...` with the `.pack`
suffix, created its `.idx` file and then dumped the output of `git
verify-pack -v` a file with the `.txt` extension. Hopefully this makes it
easier to understand the internals of how git-remote-gcrypt works.