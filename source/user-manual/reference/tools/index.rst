.. _tools:

Tools
=====

+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| Tools                                             | Descriptions                                                               | Supported installations     |
+===================================================+============================================================================+=============================+
| :doc:`ossec-control <ossec-control>`              | Manages the status of Wazuh processes                                      | Server, local, agent        |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`agent-auth <agent-auth>`                    | Adds agents to a Wazuh manager                                             | Agent                       |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`agent_control <agent_control>`              | Allows queries of the manager to get information about                     | Server                      |
|                                                   |                                                                            |                             |
|                                                   | any agent                                                                  |                             |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`manage_agents <manage_agents>`              | Provides an interface to handle authentication                             | Server, agent               |
|                                                   |                                                                            |                             |
|                                                   | keys for  agents                                                           |                             |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`ossec-logtest <ossec-logtest>`              | Allows testing and verification of rules against provided log records      | Server, local               |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`ossec-makelists <ossec-makelists>`          | Compiles cdb databases                                                     | Server, local               |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`rootcheck_control <rootcheck_control>`      | Allows management of policy monitoring                                     | Server, local               |
|                                                   |                                                                            |                             |
|                                                   | and system auditing database                                               |                             |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`syscheck_control <syscheck_control>`        | Provides an interface for managing the                                     | Server, local               |
|                                                   |                                                                            |                             |
|                                                   | integrity checking database                                                |                             |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`syscheck_update <syscheck_update>`          | Updates the integrity check database                                       | Server, local               |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`clear_stats <clear_stats>`                  | Clears the events stats                                                    | Server, local               |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`ossec-regex <ossec-regex>`                  | Validates a regex expression                                               | Server, local               |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`update-ruleset.py <update-ruleset.py>`      | Update Decoders, Rules and Rootchecks                                      | Server                      |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`util.sh <util.sh>`                          | Adds a file to be monitored by ossec-logcollector                          | Server, local, agent        |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+
| :doc:`verify-agent-conf <verify-agent-conf>`      | Verifies the Wazuh agent.conf configuration                                | Server                      |
+---------------------------------------------------+----------------------------------------------------------------------------+-----------------------------+

.. topic:: Contents

  .. toctree::
    :maxdepth: 1

    agent-auth
    agent_control
    manage_agents
    ossec-control
    ossec-logtest
    ossec-makelists
    rootcheck_control
    syscheck_control
    syscheck_update
    clear_stats
    ossec-regex
    update-ruleset.py
    util.sh
    verify-agent-conf
