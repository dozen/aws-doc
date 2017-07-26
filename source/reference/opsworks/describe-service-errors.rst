[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-service-errors:


***********************
describe-service-errors
***********************



===========
Description
===========



Describes AWS OpsWorks service errors.

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-service-errors
  [--stack-id <value>]
  [--instance-id <value>]
  [--service-error-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID. If you use this parameter, ``describe-service-errors`` returns descriptions of the errors associated with the specified stack.

  

``--instance-id`` (string)


  The instance ID. If you use this parameter, ``describe-service-errors`` returns descriptions of the errors associated with the specified instance.

  

``--service-error-ids`` (list)


  An array of service error IDs. If you use this parameter, ``describe-service-errors`` returns descriptions of the specified errors. Otherwise, it returns a description of every error.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ServiceErrors -> (list)

  

  An array of ``ServiceError`` objects that describe the specified service errors.

  

  (structure)

    

    Describes an AWS OpsWorks service error.

    

    ServiceErrorId -> (string)

      

      The error ID.

      

      

    StackId -> (string)

      

      The stack ID.

      

      

    InstanceId -> (string)

      

      The instance ID.

      

      

    Type -> (string)

      

      The error type.

      

      

    Message -> (string)

      

      A message that describes the error.

      

      

    CreatedAt -> (string)

      

      When the error occurred.

      

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
