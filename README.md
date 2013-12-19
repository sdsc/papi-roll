# SDSC "papi" roll

## Overview

This roll bundles the Performance Application Programming Interface (PAPI)
software package.

For more information about PAPI please visit the official web page:

- <a href="http://icl.cs.utk.edu/papi/" target="_blank">PAPI</a> provides the
tool designer and application engineer with a consistent interface and
methodology for use of the performance counter hardware found in most major
microprocessors.


## Requirements

To build/install this roll you must have root access to a Rocks development
machine (e.g., a frontend or development appliance).

If your Rocks development machine does *not* have Internet access you must
download the appropriate papi source file(s) using a machine that does
have Internet access and copy them into the `src/<package>` directories on your
Rocks development machine.


## Dependencies

Unknown at this time.


## Building

To build the papi-roll, execute these instructions on a Rocks development
machine (e.g., a frontend or development appliance):

```shell
% make default 2>&1 | tee build.log
% grep "RPM build error" build.log
```

If nothing is returned from the grep command then the roll should have been
created as... `papi-*.iso`. If you built the roll on a Rocks frontend then
proceed to the installation step. If you built the roll on a Rocks development
appliance you need to copy the roll to your Rocks frontend before continuing
with installation.


## Installation

To install, execute these instructions on a Rocks frontend:

```shell
% rocks add roll *.iso
% rocks enable roll papi
% cd /export/rocks/install
% rocks create distro
% rocks run roll papi | bash
```

In addition to the software itself, the roll installs papi environment
module files in:

```shell
/opt/modulefiles/applications/papi
```
