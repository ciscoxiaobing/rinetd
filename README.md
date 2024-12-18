rinetd, by Thomas Boutell and Sam Hocevar. Released under the terms
of the GNU General Public License, version 2 or later.

This program is used to efficiently redirect connections from one IP
address/port combination to another. It is useful when operating virtual
servers, firewalls and the like.

To build under Unix, run `./bootstrap` to create the configuration
files, then `./configure` to create the build files, and then type
`make` to build rinetd. To install, type `make install` as root.

For documentation run `make install`, then type `man rinetd` for
details. Or, read `index.html` in your browser.

```bash
wget https://xxx.blob.core.chinacloudapi.cn/friday/net/rinetd-0.73.tar.gz
tar -xf rinetd-0.73.tar.gz
cd rinetd-0.73/
./configure
make
make install

vim rinetd.conf
0.0.0.0 1443 10.8.0.2 9443
# 127.0.0.1   8000/udp  192.168.1.2     8000/udp     [src=192.168.1.2,timeout=1200]

cp rinetd.conf /etc/
rinetd -c /etc/rinetd.conf


[root@JumpVM ~]# ss -ntl | grep 1443
LISTEN 0      128          0.0.0.0:1443      0.0.0.0:*
```   
https://www.cloudiplc.com/index.php?rp=/knowledgebase/6/rinetdIP.html   
