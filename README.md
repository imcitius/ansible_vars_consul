# ansible_vars_consul
Ansible vars plugin, to get inventory configuration variables from Hashicorp Consul KV store.

Consul KV store should contain tree structure, starting in 'inventory-json' folder, for example:

/inventory-json/common/foo:bar - configuration level common to all inventories and projects.
/inventory-json/pgsql/bar:baz- configuration level for all hosts in 'pgsql' group.
/inventory-json/dev/common/foo:xyz - configuration level common for all hosts in 'dev' project.
/inventory-json/dev/redis/param:redis-dev - configuration level common for all hosts in group 'redis' of 'dev' project.

The script will merge all parameters in abovementioned order, so mode specific config will take precedence over common config.

Only configration parameter needed - Consul URL, set in CONSUL_KV_URL parameter inside of VarsModule class.


PR's are welcome.
