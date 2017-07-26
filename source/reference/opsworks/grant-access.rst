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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/GrantAccess>`_


========
Synopsis
========

::

    grant-access
  --instance-id <value>
  [--valid-for-in-minutes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance's AWS OpsWorks Stacks ID.

  

``--valid-for-in-minutes`` (integer)


  The length of time (in minutes) that the grant is valid. When the grant expires at the end of this period, the user will no longer be able to use the credentials to log in. If the user is logged in at the time, he or she automatically will be logged out.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The instance's AWS OpsWorks Stacks ID.

    

    

  

