Collecting remote Syslog
========================

For other devices like firewalls, you can configure Wazuh manager to receive log events through syslog. This need to be configured in the :doc:`ossec.conf <../reference/configuration/ossec-conf/index>`using the :doc:`Remote <../reference/configuration/ossec-conf/remote>` option.

Configuration example:
::

  <ossec_config>
    <remote>
      <connection>syslog</connection>
      <allowed-ips>192.168.2.0/24</allowed-ips>
    </remote>
  <ossec_config>

- ``<connection>syslog</connection>`` indicates the manager will accept incoming syslog messages from across the network
- ``<allowed-ips>192.168.2.0/24</allowed-ips>`` defines the network from which syslog messages will be accepted.
