# 制作自己的homeassistant集成configurator
打开原homeassistant容器
'''
mkdir /config/hass_configurator && cd /config/hass_configurator
wget configurator.py
wget settings.conf
chmod 755 configurator.py
cd /config
python3 ./hass_configurator/configurator.py ./hass_configurator/settings.conf &
'''
我的settings.conf
'''
{
    "LISTENIP": "0.0.0.0",
    "LISTENPORT": 8124,
    "BASEPATH": null,
    "SSL_CERTIFICATE": null,
    "SSL_KEY": null,
    "HASS_API": "http://192.168.100.200:8123/api/",
    "HASS_API_PASSWORD": null,
    "CREDENTIALS": null,
    "ALLOWED_NETWORKS": [],
    "BANNED_IPS": [],
    "BANLIMIT": 0
}
'''
我的configuration.yaml
'''
# cat configuration.yaml 添加
panel_iframe:
  configurator:
    title: 'Configurator'
    url: 'http://192.168.100.200:8124'
    icon: mdi:wrench
'''
