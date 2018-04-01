# rpi_flexget_conf

'config.yml' requires to have another file within same folder:

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
