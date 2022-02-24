# gh-bulk-clone

Installation: `gh extension install https://ghe.ckpd.co/uasi/gh-bulk-clone`

## `gh bulk-clone`

```
usage: gh bulk-clone <repo-list-file> <output-dir> [<sparse-checkout-pattern>...] [-- <clone-option>...]"
```

### Examples

```
$ cat <<END > repos.txt
git@ghe.ckpd.co:tech/cookpad_all.git
git@ghe.ckpd.co:tech/next-cookpad.git
END

$ gh bulk-clone repos.txt repos 'Gemfile*' -- --depth=1 --filter=blob:none
(snip)

$ find repos -name 'Gemfile*' | head -n10
repos/tech/next-cookpad/dev/Gemfile
repos/tech/next-cookpad/dev/Gemfile.lock
repos/tech/cookpad_all/pantry/Gemfile_edge.lock
repos/tech/cookpad_all/pantry/Gemfile.shared
repos/tech/cookpad_all/pantry/Gemfile
repos/tech/cookpad_all/pantry/Gemfile.lock
repos/tech/cookpad_all/pantry/Gemfile_edge
repos/tech/cookpad_all/papa/Gemfile_edge.lock
repos/tech/cookpad_all/papa/Gemfile.shared
repos/tech/cookpad_all/papa/Gemfile
```
