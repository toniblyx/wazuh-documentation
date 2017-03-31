.. _daemons:

Daemons
=======

+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| Daemons                                           | Descriptions                                                    | Supported installations     |
+===================================================+=================================================================+=============================+
| :doc:`ossec-agentd <ossec-agentd>`                | Client side daemon that communicates                            | Agent                       |
|                                                   |                                                                 |                             |
|                                                   | with the server                                                 |                             |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-agentlessd <ossec-agentlessd>`        | Runs integrity checking on systems without                      | Server, local               |
|                                                   |                                                                 |                             |
|                                                   | an agent installed                                              |                             |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-analysisd <ossec-analysisd>`          | Receives log messages and compares                              | Server, local               |
|                                                   |                                                                 |                             |
|                                                   | them to the rules                                               |                             |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-authd <ossec-authd>`                  | Adds agents to Wazuh manager                                    | Server                      |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-csyslogd <ossec-csyslogd>`            | Forwards Wazuh alerts via syslog                                | Server, local               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-dbd <ossec-dbd>`                      | Inserts alert logs into a database                              | Server, local               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-execd <ossec-execd>`                  | Executes active responses                                       | Server, local, agent        |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-logcollector <ossec-logcollector>`    | Monitors configured files and commands for                      | Server, local, agent        |
|                                                   |                                                                 |                             |
|                                                   | new log messages                                                |                             |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-maild <ossec-maild>`                  | Sends Wazuh alerts via email                                    | Server, local               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-monitord <ossec-monitord>`            | Monitors agent connectivity and compresses log files            | Server, local               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-remoted <ossec-remoted>`              | Communicates with agents                                        | Server                      |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-reportd <ossec-reportd>`              | Creates reports from Wazuh alerts                               | Server, local               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`ossec-syscheckd <ossec-syscheckd>`          | Checks configured files for security changes                    | Server, local, agent        |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+
| :doc:`wazuh-modulesd <wazuh-modulesd>`            | Wazuh module manager                                            | Server, agent               |
+---------------------------------------------------+-----------------------------------------------------------------+-----------------------------+


.. topic:: Contents

    .. toctree::
        :maxdepth: 1

        ossec-agentd
        ossec-agentlessd
        ossec-analysisd
        ossec-authd
        ossec-csyslogd
        ossec-dbd
        ossec-execd
        ossec-logcollector
        ossec-maild
        ossec-monitord
        ossec-remoted
        ossec-reportd
        ossec-syscheckd
        wazuh-modulesd
