# TICK Stack #


## Create directory structure ##
```
mkdir -p confs/{telegraf,telegraf/telegraf.d,kapacitor,influxdb}
```

## Generate Telegraf configuration ##

```
docker run --rm telegraf telegraf config > ./confs/telegraf/telegraf.conf
```

### Modify telegraf configuration ###

```
[[outputs.influxdb]]
  urls = ["http://influxdb:8086"]
  database = "telegraf" 
  retention_policy = ""
  write_consistency = "any"
  timeout = "5s"
  username = "telegraf"
  password = "password"
```

## Telegraf Plugins ##

Telegraf plugins are defined in `confs/telegraf/telegraf.d/`

```
cpu.conf  disk.conf  docker.conf  kernel.conf  mem.conf  net.conf  netstat.conf  processes.conf  system.conf
```

## Modify .env with correct data ##

```
cp .env.example .env
```
