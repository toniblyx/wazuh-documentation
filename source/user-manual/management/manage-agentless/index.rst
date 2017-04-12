.. _manual_agentless:


Manage agentless
======================

Agentless monitoring allows you to monitor devices or systems with no agent using SSH, such as: routers, firewalls, switches and linux/bsd systems.

Connection
----------

First of all, agentless monitoring must be enabled:

.. code-block:: console

  /var/ossec/bin/ossec-control enable agentless

In order to connect the manager to the device using SSH authentication, the following script should be used: ``register_host.sh``, which is located in: ``/var/ossec/agentless/``  This script has two options: ``list``  and ``add``.

Using the ``list`` option will list all hosts already included.

.. code-block:: console

  /var/ossec/agentless/register_host.sh list

Using the ``add`` option will specify a new device to be added to the manager. ``NOPASS`` may be entered as the password to use public key authentication rather than using a password.  For Cisco devices, such as routers or firewalls, ``enablepass`` should be used to specify the enable password.

.. code-block:: console

  /var/ossec/agentless/register_host.sh add root@example_address.com example_password [enablepass]

Public key authentication can be used with the following command:

.. code-block:: console

  sudo -u ossec ssh-keygen

Once created, the public key must be copied into the remote device.
