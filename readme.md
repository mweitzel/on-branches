# on-branches

iterate over git branches to perform a command

## installation

throw `on-branches` in your `$PATH`

## usage

run as `on-brances branch0 branch1 branchN -- command to run`

```bash
$ on-branches master feature -- echo do stuff like checking performance here
##
##  Already on 'master'
##  running: echo do stuff like check performance
do stuff like check performance
##
##  Switched to branch 'feature'
##  running: echo do stuff like check performance
do stuff like check performance
##
##  returning to original branch, 'master'
##  Switched to branch 'master'
```

you can pass bash -c and a command string to send more complex commands:

this allows the provided commands to be pipelines

```bash
$ ./on-branches master feature -- bash -c 'echo oh hello hi there man | grep -o "hi there"'
##
##  Already on 'master'
##  running: bash -c 'echo oh hello hi there man | grep -o "hi there"'
hi there
##
##  Switched to branch 'feature'
##  running: bash -c 'echo oh hello hi there man | grep -o "hi there"'
hi there
##
##  returning to original branch, 'master'
##  Switched to branch 'master'
```

## license

MIT
