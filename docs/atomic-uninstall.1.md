% ATOMIC(1) Atomic Man Pages
% Dan Walsh
% January 2015
# NAME
atomic-uninstall - Remove/Uninstall container/container image from system

# SYNOPSIS
**atomic uninstall**
[**-h**]
IMAGE

# DESCRIPTION
**atomic uninstall** attempts to read the `LABEL UNINSTALL` field in the
container IMAGE, if this field does not exists **atom uninstall** will just
uninstall the image.

If the contaimer image has a LABEL UNINSTALL instruction like the folling:

```LABEL UNINSTALL /usr/bin/docker run -t -i --rm --privileged -v /:/host --net=host --ipc=host --pid=host -e HOST=/host -e NAME=NAME -e IMAGE=IMAGE -e CONFDIR=${CONFDIR} -e LOGDIR=${LOGDIR} -e DATADIR=${DATADIR} --name NAME IMAGE /bin/uninstall.sh```

`atomic uninstall` will replace the NAME and IMAGE fields with the name and
image specified via the command,  `atomic uninstall` will also pass in the CONFDIR, LOGDIR and DATADIR environment variables to the container.


# OPTIONS:
**--help**
  Print usage statement

**--name**=""
   If name is specified `atomic uninstall` will uninstall the named container from the system, otherwise it will uninstall the container images.

# HISTORY
January 2015, Originally compiled by Daniel Walsh (dwalsh at redhat dot com)
