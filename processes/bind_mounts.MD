
# Hidden linux process with bind mounts

https://righteousit.com/2024/07/24/hiding-linux-processes-with-bind-mounts/



# view
`cat /proc/mounts | grep /proc`

`cat /proc/*/mounts | awk '$2 ~ /^\/proc\/[0-9]*($|\/)/ { print $2 }' | sort -ur`
