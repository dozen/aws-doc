[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks grant-access:


************
grant-access
************



===========
Description
===========



.. note::

  This action can be used only with Windows stacks.

 

Grants RDP access to a Windows instance for a specified time period.



========
Synopsis
========

::

    grant-access
  --instance-id <value>
  [--valid-for-in-minutes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance's AWS OpsWorks ID.

  

``--valid-for-in-minutes`` (integer)


  The length of time (in minutes) that the grant is valid. When the grant expires at the end of this period, the user will no longer be able to use the credentials to log in. If the user is logged in at the time, he or she automatically will be logged out.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TemporaryCredential -> (structure)

  

  A ``TemporaryCredential`` object that contains the data needed to log in to the instance by RDP clients, such as the Microsoft Remote Desktop Connection.

  

  Username -> (string)

    

    The user name.

    

    

  Password -> (string)

    

    The password.

    

    

  ValidForInMinutes -> (integer)

    

    The length of time (in minutes) that the grant is valid. When the grant expires, at the end of this period, the user will no longer be able to use the credentials to log in. If they are logged in at the time, they will be automatically logged out.

    

    

  InstanceId -> (string)

    

    The instance's AWS OpsWorks ID.

    

    

  

