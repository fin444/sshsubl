# sshsubl
A simple BASH script to edit files in Sublime Text over SSH - no plugins or port forwarding necessary!

## Usage

Depends on `inotify-tools` (on local machine)

```
sshsubl user@host /absolute/path/to/file
```

I find it convenient to add the following to my remote `.bash_aliases`:

```
function subl {
    echo "sshsubl user@host `realpath $1` &"
}
```

## Limitations

* Does not update the local version if the remote version is changed through other means
* Causes a local memory leak if the script is ended before you close the file in Sublime Text
* Expects you to use it correctly - minimal error handling
