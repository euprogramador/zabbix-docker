# Goal

Monitor resource used by running containers


# Requirements

## docker-py library 

``` 
# pip install docker-py
```

or
```
# git clone git@github.com:docker/docker-py.git
# cd docker-py
# python setup.py install
```

## py-zabbix library 

```
# pip install py-zabbix
```
or

```
# git clone git@github.com:blacked/py-zabbix.git
# cd py-zabbix
# python setup.py install
```

## Packages used

* python 2.7.9
* docker 1.6
* zabbix agent and server 2.4

# Initial Configuration

## Docker host server

```
# apt-get install zabbix-agent
# git clone https://github.com/euprogramador/zabbix-docker.git
# cd zabbix-docker
# cp *.py /etc/zabbix
# chown -R zabbix /etc/zabbix/
# chmod u+x /etc/zabbix/*.py
# echo 'Defaults:username !requiretty' >> /etc/sudoers
# echo "EnableRemoteCommands=1" >> /etc/zabbix/zabbix_agentd.conf
# echo "Timeout=30" >> /etc/zabbix/zabbix_agentd.conf
# echo "zabbix ALL=NOPASSWD: /etc/zabbix/list_containers_docker_lld.py" >> /etc/sudoers
# echo "*/5 * * * *   root /etc/zabbix/docker_stats.py" > /etc/cron.d/docker-zabbix
```

Configure o servidor do zabbix
e o hostname



