# [Runit](https://smarden.org/runit/)

## Boot

 runit performs the system's booting, running and shutting down in three stages:

- Stage 1: `runit` starts `/etc/runit/1` and waits for it to terminate. The system's one time initialization tasks are done here.  
  `/etc/runit/1` has full control over `/dev/console` to be able to start an emergency shell in case the one time initialization tasks fail.
- Stage 2: `runit` starts `/etc/runit/2` which should not return until the system is going to halt or reboot; if it crashes, it will be restarted.
  Normally, `/etc/runit/2` runs `runsvdir`. 
- Stage 3: If `runit` is told to halt or reboot the system, or Stage 2 returns without errors, it terminates Stage 2 if it is running, and runs `/etc/runit/3`. The systems tasks to shutdown and halt or reboot are done here.


## Runlevels

**Runlevels** are stored in `/etc/runit/runsvdir/`. The name of the directory is the name of the runlevel.

Adding a service to a runlevel is done by linking the service file (usually under `/etc/sv/<service>`) to `/etc/runit/runsvdir/<runlelev>`.

Switching to a runlevel is done by switching the directory `runsvdir` is runniing in with `runsvchdir <runlevel>`.

