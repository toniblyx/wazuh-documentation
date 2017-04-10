FAQ
===

Log-Analysis
------------

#. `Are the logs analyzed on each agent?`_
#. `How often does the manager monitor the logs?`_
#. `How long are the logs stored on the server?`_
#. `How does this help me with regulatory compliance?`_
#. `What is the CPU usage like on the agents for log analysis?`_
#. `From where can Wazuh get log messages?`_
#. `Can I send firewall, vpn, authentication logs to Wazuh?`_
#. `What information should Wazuh extract from my logs?`_
#. `Can I ignore events that are not important?`_
#. `Can I check if an application is running on an agent?`_

File integrity monitoring
-------------------------

#. `How often does syscheck run?`_
#. `What is the CPU usage like on the agents for fim?`_
#. `Where are all the checksums stored?`_
#. `Can I ignore files in a directory?`_
#. `Can Wazuh report changes in the content of a text file?`_
#. `How does Wazuh verify the integrity of files?`_
#. `Does Wazuh monitor any directories by default?`_
#. `Can I force an inmediate syscheck scan?`_
#. `Does Syscheck start when Wazuh start?`_
#. `Does Wazuh alert when a new file is created?`_


Anomaly detection
-----------------

#. `How often does rootcheck run?`_
#. `How does rootcheck know the rootkit files to look for?`_
#. `Does rootcheck inspect running processes?`_
#. `What about hidden files?`_

Policy monitoring
-----------------

#. `Can I specify my own audit file for policy monitoring?`_
#. `Is there a noticeable performance impact when the OpenSCAP wodle is enabled on an agent?`_
#. `Are evaluations executed in parallel?`_
#. `How does the interval work?`_
#. `Are the policies evaluated when OSSEC starts?`_
#. `Where are the policies?`_

Automatic remediation
---------------------

#. `Can I use a custom script?`_
#. `Can I configure active response to only one host?`_
#. `Can active response remove the action after a time?`_

Running remote commands
-----------------------

#. `Can I monitor commands on Linux or Windows?`_
#. `What are the possibilities of this capability?`_

Are the logs analyzed on each agent?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

No, the manager gets the logs from all the agents and then analyzes the messages.

How often does the manager monitor the logs?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The manager monitors logs in real time.

How long are the logs stored on the server?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Archived logs are not automatically deleted.  You choose when to manually or automatically (i.e., cron job) delete logs according to your own legal and regulatory requirements.

How does this help me with regulatory compliance?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Log analysis is a requirement for : :ref:`PCI DSS Compliance <pci_dss_log_analysis>`,  HIPAA Compliance, FISMA Compliance and SOX Compliance.

What is the CPU usage like on the agents for log analysis?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^-

The memory and CPU requirements of the agent are insignificant because it mostly just forwards events to the manager.  However, on the manager, CPU and memory consumption can increase quickly depending on the events per second (EPS) that the manager has to analyze.

From where can Wazuh get log messages?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wazuh can read log messages from text log files, Windows event logs and event channels, and also via remote syslog.  Logs are monitored in real time.

Can I send firewall, VPN, authentication logs to Wazuh?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes. Wazuh has the capability to receive and process logs from devices that send logs using the syslog protocol. You can create custom decoders and rules for your device-specific logs.

What information should Wazuh extract from my logs?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This depends on your needs. Once you know the format of your application logs and the typical events, you can create decoders and rules for them.

Can I ignore events that are not important?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can configure the rules to ignore certain events. More info: :ref:`Custom rules <ruleset_custom>`

Can I check if an application is running on an agent?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Yes, it's possible to monitor running applications. :ref:`Example <log-analysis-examples>`

How often does syscheck run?
--------------------------------
Syscheck frequency is configurable by the user with :ref:`frequency <reference_ossec_syscheck_frequency>`. By default is configured to run every 6 hours.

What is the CPU usage like on the agents for fim?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Syscheck scans are designed to run slowly to avoid too much CPU or memory use.

Where are all the checksums stored?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

All the checksums are stored on the manager ``/var/ossec/queue/syscheck``

Can I ignore files in a directory?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, you can use the :ref:`ignore <reference_ossec_syscheck_ignore>` option to avoid false positives. Example: :ref:`ignore-false-positives <how_to_fim_ignore>`

Can Wazuh report changes in the content of a text file?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, this is posible with the ``report_changes`` option.  For ``directories`` only. This option gives us the exact content that has been changed in a text file. Be selective about which folders you use ``report_changes`` on, because this requires syscheck to copy every single file you want to monitor with ``report_changes`` to a private location for comparison purposes.
Example: :ref:`report changes <how_to_fim_report_changes>`

How does Wazuh verify the integrity of files?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wazuh manager stores and looks for modifications to all the checksums and file attributes received from the agents for the monitored files. Wazuh manager compares the new checksums/attributes against the stored ones. An alert is generated if anything changes.

Does Wazuh monitor any directories by default?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes. By default Wazuh monitors ``/etc``, ``/usr/bin``, ``/usr/sbin``, ``/bin`` and ``/sbin`` on Unix-like systems and ``C:\Windows\System32`` on Windows.

Can I force an inmediate syscheck scan?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, you can force an agent to perform a system integrity check with ::
  /var/ossec/bin/agent_control -r -a
  /var/ossec/bin/agent_control -r -u <agent_id>

More info at :ref:`Ossec control section <ossec-control>`

Does Syscheck start when Wazuh start?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

By defult syscheck scan when Wazuh start, but you can change this with the :ref:`scan_on_start option<reference_ossec_syscheck_scan_start>`

Does Wazuh alert when a new file is created?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, but you need to configure it. Use the :ref:`alert_new_files option<reference_ossec_syscheck_alert_new_files>`

How often does rootcheck run?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The rootcheck scan frequency is configurable with :ref:`frequency <reference_ossec_rootcheck_frequency>`. By default it runs every 2 hours.

How does rootcheck know the rootkit files to look for?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The rootcheck engine has databases of rootkit signatures: *rootkit_files.txt*, *rootkit_trojans.txt* and *win_malware_rcl.txt*. Unfortunately, the signatures are out of date.

Does rootcheck inspect running processes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Yes, rootcheck inspects all running processes looking for discrepancies with different system calls.

What about hidden files?
^^^^^^^^^^^^^^^^^^^^^^^^^^
The rootcheck engine scans the entire system comparing the differences between the *stat size* and the files size when using the *fopen* + *read* calls.  If any results do not match, you might have a malware installed.

Can I specify my own audit file for policy monitoring?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, you can use the *system_audit* option for that.  Example :ref:`SSH rule <how_to_rootcheck_ssh>`

Is there a noticeable performance impact when the OpenSCAP wodle is enabled on an agent?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The OpenSCAP wodle is designed to be very efficient, but the performance will depend on how fast oscap is (the scanner). Depending on the chosen policy, oscap can consume significant resources. We recommend you test your policies on a test agent before deploying them to production systems.


Are evaluations executed in parallel?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

No, each evaluation is executed sequentially.  Also, each profile of an evaluation is executed sequentially.  This makes scans take somewhat longer but also reduces the load on agents caused by those scans.


How does the interval work?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The interval is the intended amount of time between the commencements of subsequent OpenSCAP scans on an agent.  If a scan takes longer than the configured interval, an "interval overtaken" log message will be written to /var/ossec/log/ossec.log, and when the scan is finished, it will start again immediately.


Are the policies evaluated when OSSEC starts?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yes, by default, policies are evaluated when the wodle starts. You can change this by setting <scan-on-start> to 'no'. In this case, the next evaluation will be executed after the interval specified. The wodle state is saved when OSSEC is stopped.


Where are the policies?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Each agent must have its policies in ``/var/ossec/wodles/oscap/policies``.

Can I use a custom script?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Yes. You can create your own script and configure a command and active response to refer to it.

Can I configure active response to only one host?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Yes, using the location option. More info: :ref:`Active Response options <reference_ossec_active_response>`

Can active response remove the action after a time?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Yes, using the *timeout_allowed* option on the command and the *timeout* option on the active response. More info: :ref:`Example <remediation-examples>`

Can I monitor commands on Linux or Windows?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You can monitor command output on both Linux and Windows systems.

What are the possibilities of this capability?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Some examples: Disk space utilization, detection if an important process is running or not, load average, change in network listeners...
