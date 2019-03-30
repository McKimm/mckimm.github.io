Testing VMs running LINUX:
Use nttcp-for-linux. It is available from https://github.com/Microsoft/ntttcp-for-linux

On the Linux VMs (both SENDER and RECEIVER), run these commands to prepare ntttcp-for-linux on your VMs:

CentOS - Install Git:

```bash
  yum install gcc -y
  yum install git -y
```
Ubuntu - Install Git:


```bash
 apt-get -y install build-essential
 apt-get -y install git
```
Make and Install on both:


```bash
 git clone https://github.com/Microsoft/ntttcp-for-linux
 cd ntttcp-for-linux/src
 make && make install
As in the Windows example, we assume the Linux RECEIVER's IP is 10.0.0.4
```
Start NTTTCP-for-Linux on the RECEIVER:


```bash
ntttcp -r -t 300
```
And on the SENDER, run:


```bash
ntttcp -s10.0.0.4 -t 300
```
Test length defaults to 60 seconds if no time parameter is given
