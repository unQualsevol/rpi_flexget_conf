# rpi_flexget_conf

The purpose of this project is to keep my Raspberry Pi's FlexGet configuration file.


# My config.yml 

Requires to have another file within same folder:

**secrets.yml** with the following format:

```
trans:
  host: aaa
  user: bbb
  password: ccc
email:
  from: ddd
  to: eee
  user: fff
  password: hhh
url:
  anime: iii
  tv: jjj
```

The purpose is to have the secrets/personal stuff in a file that's not shared.

This works by using FlexGet's [variables](https://flexget.com/Plugins/variables) plugin

## Run at system startup

As suggested in FlexGet documentation: [Scheduling](https://flexget.com/InstallWizard/Linux/Scheduling)

```
crontab -e
```

add the following line:

```
@reboot /usr/local/bin/flexget daemon start -d --autoreload-config
```

The **--autoreload-config** flag makes the process to detect changes in **config.yml** file and then reload it when necessary.

Don't forget to enable **cron**, for example the RPis seems to have it disabled by default.

```
sudo systemctl enable cron
```
