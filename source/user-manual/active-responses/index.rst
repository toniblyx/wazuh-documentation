.. _automatic_remediation:

Active Responses
================

Active response performs various countermeasures to address active threats such as blocking access to an agent from the threat source.

Active response executes a script in response to being triggered by a specific alert based on alert level or rule group. Any number of scripts can be initiated in response to a trigger, however these responses should be carefully considered as poor implementation of rules and responses could increase the vulnerability of the system.

Active response is configured in :ref:`ossec.conf <reference_ossec_conf>`, within the :ref:`Active Response <reference_ossec_active_response>` and :ref:`Command <reference_ossec_commands>` sections.

.. topic:: Contents

    .. toctree::
        :maxdepth: 1

        ar-configuration
        ar-examples
        remediation-faq
