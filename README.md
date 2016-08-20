# tarantool-munin
Munin plugins for Tarantool 1.6+

###Requires
* [Tarantool] - is an in-memory database and application server.
* [PHP] 5.4+ (Testing on PHP 7.0.8)
* [Tarantool PHP] extension, if you are using php 5.x you need install master branch, if you are using php 7.x you need install php7-v1 branch 
* [Munin] - monitoring tool surveys all your computers and remembers what it saw.

###Installation for Linux
```sh
cd ~
git clone https://github.com/baltazor5000/tarantool-munin.git
cd tarantool-munin
sudo mv tarantool_* /usr/share/munin/plugins/
cd /etc/munin/plugin-conf.d/
sudo printf "[tarantool_*]\n \t env.HOST 127.0.0.1\n \t env.PORT 3301 " > tarantool
cd /etc/munin/plugins/
sudo ln -s /usr/share/munin/tarantool_memory
sudo ln -s /usr/share/munin/tarantool_stats
sudo ln -s /usr/share/munin/tarantool_uptime
sudo service munin-node restart
OR
sudo systemctl restart munin-node
```


[Tarantool]:https://tarantool.org
[PHP]:http://php.net
[Tarantool PHP]:https://github.com/tarantool/tarantool-php
[Munin]:http://munin-monitoring.org
