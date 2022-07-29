Create Zirrus One Zabbix proxies on docker.

Usage:

1. Create a branch for the machine that you're on, being sure to substitute the hostname:
```
 git checkout -b qbox123 
```

2. Create a psk-key. Note that you'll need the output of this command when adding the proxy configuration to zabbix server (e.g., mon.aws.zirrusone.com). BE SURE TO NOTE IT.

 mkdir -p zbx_env/var/lib/zabbix/enc
 hexdump -vn16 -e'4/4 "%08X" 1 "\n"' /dev/urandom | sudo tee zbx_env/var/lib/zabbix/enc/z1-psk

3. Edit environment variables appropriately inside env_vars/.env_prx:
 vim env_vars/.env_prx

4. Launch the proxy:
 docker-compose up -d zabbix-proxy-sqlite3
