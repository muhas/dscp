# dscp — frontend for scp and ssh (dsh like)

## Usage

```
dscp servergroup cp from to
dscp servergroup command
```

## Installation

Copy this one-liner and run it in your shell

```
DSCP='/usr/local/bin/dscp' && curl -o $DSCP https://raw.githubusercontent.com/muhas/dscp/master/bin/dscp && chmod +x $DSCP && unset DSCP
```
Note: Use sudo or replace /usr/local/bin/dscp to path somewhere inside your home directory.


## Examples

dsh server group
```
# cat /.dsh/group/servergroup
server1
server2
server3
```

### one way scp
```
dscp servergroup cp ~/testfile /tmp/test
```
runing
```
scp ~/testfile server1:/tmp/test
scp ~/testfile server2:/tmp/test
scp ~/testfile server3:/tmp/test
```
### dsh like run
```
dscp servergroup uname -a
```
runing
```
ssh server1 uname -a
ssh server2 uname -a
ssh server3 uname -a
```

## Why?

**dsh** does not work in my phone and raspberry pi, so I wrote a simple replacement, and since sometimes I use copying a file to multiple servers, I also added the copy function
Perhaps it will be useful to someone other than me