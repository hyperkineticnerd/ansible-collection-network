= Ansible Collection - hyperkineticnerd.network

This collection allows network engineers to manage a large enterprise configuration utilizing multiple vendors.

== Usage

=== Built-in playbooks

There is currently a single usable playbook for backing up switch configurations. Usage is `ansible-playbook hyperkineticnerd.network.backup`

=== Writing your own playbook

Your inventory can be organized at several layers and at the device, device role, site, and enterprise levels.  It does increase complexity of management, but gives granularity to configuration and to reduce repeating the same configuration at the device level.

Your playbooks can just use, for example, the `hyperkineticnerd.network.vlan` role to combine your device roles (edge, core, router, firewall) and site configurations within your inventory to build a full switch/router configuration.

=== Creating your inventories

To begin building out your inventory, first create your main inventory file `inventories/hosts.yml`. This file will define your switches, routers, and security gateways. Next start building your `group_vars` folder and `host_vars` folder (if you don't want to include all the host-based variables within hosts.yml). `group_vars` under `inventories` will contain vendor and device model folders for each of your switches. `group_vars` will also include role folders and site folders which will help Ansible colligate all variables together. Your Role groups will hold settings for each switch role you define. Your site groups are for settings like SNMP or switch owner contact information.
