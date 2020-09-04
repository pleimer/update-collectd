This is a temporary convenience playbook that updates all plugin configurations for every collectd container on an OpenStack cloud deployed with infrared. Once configurations have been updated on each node, the collectd containers are restarted so that the new configs take effect.

# Usage
To run, you must be logged into the machine on which openstack was deployed infrared. Run:

```
. ~/infrared/.venv/bin/activate
git clone https://github.com/pleimer/update-collectd
cd update-collectd

ansible-playbook -i $(infrared workspace inventory) update-collectd.yaml
```

# Changing Collectd Configurations
Add or remove collectd plugins by updating the `collectd_plugins` variable. 

Change plugin configurations by setting the corresponding variable used in the Jinja2 template (roles/collectd-config-ansible-role/\<plugin name>.conf.j2.
