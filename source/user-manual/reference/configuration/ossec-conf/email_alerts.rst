.. _reference_ossec_email_alerts:

email_alerts
============

.. topic:: XML section name

	.. code-block:: xml

		<email_alerts>

This extends the email options configured in the ``<global>`` section.

.. note::
  `Global  <./global>`_  email configuration is necessary to use granular email options.

Options
-------

- `email_to`_
- `level`_
- `group`_
- `event_location`_
- `format`_
- `rule_id`_
- `do_not_delay`_
- `do_not_group`_


email_to
^^^^^^^^

This specifies a single email address to which to send email alerts. If you want to send alerts to multiple addresses, each address must be listed in a separate <email_to> section.  Lists are not allowed.

+--------------------+-------------------------------------+
| **Default Value**  | n/a                                 |
+--------------------+-------------------------------------+
| **Allowed values** | Any valid email address is allowed. |
+--------------------+-------------------------------------+


level
^^^^^^^^

This is the minimum alert severity level for which emails will be sent.


.. note::
  The ``level`` option should be set at or above the :ref:`email_alert_level <reference_ossec_alerts_ea>` in the ``<alerts>`` section of the configuration.

+--------------------+-------------------------------------+
| **Default Value**  | n/a                                 |
+--------------------+-------------------------------------+
| **Allowed values** | Any alert level 0 to 16 is allowed. |
+--------------------+-------------------------------------+


group
^^^^^^^^

This limits the sending of emails to only when rules are tripped that belongs to one of the listed groups.

+--------------------+-------------------------------------------------------------------------------------------------------------+
| **Default Value**  | n/a                                                                                                         |
+--------------------+-------------------------------------------------------------------------------------------------------------+
| **Allowed values** | One or more groups or categories can be used. Multiple groups can be separated with a pipe character (“|”). |
+--------------------+-------------------------------------------------------------------------------------------------------------+

event_location
^^^^^^^^^^^^^^^^

The alert must match this event location to be forwarded.
Do not specify this option repeatedly, as only the last instance would be used.

+--------------------+---------------------------------------------------------------------+
| **Default Value**  | n/a                                                                 |
+--------------------+---------------------------------------------------------------------+
| **Allowed values** | Any single agent name, hostname, IP address, or log file is allowed |
+--------------------+---------------------------------------------------------------------+


format
^^^^^^^^

This specifies the email format.

+--------------------+-----------+
| **Default Value**  | full      |
+--------------------+-----------+
| **Allowed values** | full, sms |
+--------------------+-----------+

- full: Send normal emails.

- sms: Use a compact format more suitable for SMS.


rule_id
^^^^^^^^

This limits the sending of emails to only when rules are tripped that have one of the listed rule IDs.

+--------------------+-----------------------------------------------------------------------------------+
| **Default Value**  | n/a                                                                               |
+--------------------+-----------------------------------------------------------------------------------+
| **Allowed values** | One or more rule IDs can be used here, separated by a comma and a space ( ", " ). |
+--------------------+-----------------------------------------------------------------------------------+

do_not_delay
^^^^^^^^^^^^^

This causes email alerts to be sent right away, rather than to be delayed for the purpose of batching multiple alerts together.

+--------------------+-----------------------+
| **Default Value**  | n/a                   |
+--------------------+-----------------------+
| **Allowed values** | XML tag with no value |
+--------------------+-----------------------+


do_not_group
^^^^^^^^^^^^^^

This disables grouping of multiple alerts into the same email.

+--------------------+-----------------------+
| **Default Value**  | n/a                   |
+--------------------+-----------------------+
| **Allowed values** | XML tag with no value |
+--------------------+-----------------------+

.. warning::
	Notice that **do_not_delay** and **do_not_group** are special empty-element XML tags, so they stand alone, not having a starting and ending version of the tag.  This is indicated by the tag name containing "/" at the end of the name.
