.. _manual_agentless:


Agentless monitoring
======================

Agentless monitoring allows you to monitor devices or systems with no agent using SSH or syslog, such as: routers, firewalls, switches and linux/bsd systems.

Agentless monitoring allows users who have software installation restriction meet security and compliance requirements.

Alerts will be triggered when the checksum on the output changes and will show either the checksum or the exact diff output of the change.

Agentless monitoring is configured in the :doc:`ossec.conf <../reference/configuration/ossec-conf/index>` file in the section :doc:`Agentless <../reference/configuration/ossec-conf/agentless>` or :doc:`Remote <../reference/configuration/ossec-conf/remote>`.

.. topic:: Contents

    .. toctree::
        :maxdepth: 1

        agentless-ssh
        agentless-syslog
        agentless-examples
        agentless-faq
