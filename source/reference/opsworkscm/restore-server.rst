[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm restore-server:


**************
restore-server
**************



===========
Description
===========



Restores a backup to a server that is in a ``CONNECTION_LOST`` , ``HEALTHY`` , ``RUNNING`` , ``UNHEALTHY`` , or ``TERMINATED`` state. When you run RestoreServer, the server's EC2 instance is deleted, and a new EC2 instance is configured. restore-server maintains the existing server endpoint, so configuration management of the server's client devices (nodes) should continue to work. 

 

This operation is asynchronous. 

 

An ``InvalidStateException`` is thrown when the server is not in a valid state. A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/RestoreServer>`_


========
Synopsis
========

::

    restore-server
  --backup-id <value>
  --server-name <value>
  [--instance-type <value>]
  [--key-pair <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--backup-id`` (string)


  The ID of the backup that you want to use to restore a server. 

  

``--server-name`` (string)


  The name of the server that you want to restore. 

  

``--instance-type`` (string)


  The type of the instance to create. Valid values must be specified in the following format: ``^([cm][34]|t2).*`` For example, ``m4.large`` . Valid values are ``t2.medium`` , ``m4.large`` , and ``m4.2xlarge`` . If you do not specify this parameter, restore-server uses the instance type from the specified backup. 

  

``--key-pair`` (string)


  The name of the key pair to set on the new EC2 instance. This can be helpful if the administrator no longer has the SSH key. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To restore a server**

The following ``restore-server`` command performs an in-place restoration of a 
Chef Automate server named ``automate-06`` in your default region from a backup
with an ID of ``automate-06-2016-11-22T16:13:27.998Z``. Restoring a server restores
connections to the nodes that the Chef Automate server was managing at the time 
that the specified backup was performed.

  aws opsworks-cm restore-server --backup-id "automate-06-2016-11-22T16:13:27.998Z" --server-name "automate-06"

The output is the command ID only.
*Output*::

  (None)

**More Information**

For more information, see `Restore a Failed AWS OpsWorks for Chef Automate Server`_ in the *AWS OpsWorks User Guide*.

.. _`Restore a Failed AWS OpsWorks for Chef Automate Server`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-chef-restore.html


======
Output
======

