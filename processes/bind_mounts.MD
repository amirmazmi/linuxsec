
# Hidden linux process with bind mounts

https://righteousit.com/2024/07/24/hiding-linux-processes-with-bind-mounts/


<br>

### View procs
`cat /proc/mounts | grep /proc`  
`cat /proc/*/mounts | awk '$2 ~ /^\/proc\/[0-9]*($|\/)/ { print $2 }' | sort -ur`


<br>

### Mount procs
`mount -B /proc/<target> /proc/<proc to mount>`

<br>

### Unmount proc
`cat /proc/*/mounts | awk '$2 ~ /^\/proc\/[0-9]*($|\/)/ { print $2 }' | sort -ur | while read dir; do umount $dir; done`
