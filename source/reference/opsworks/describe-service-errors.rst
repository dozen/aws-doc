[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-service-errors:


***********************
describe-service-errors
***********************



===========
Description
===========



Describes AWS OpsWorks Stacks service errors.

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .

 

This call accepts only one resource-identifying parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeServiceErrors>`_


========
Synopsis
========

::

    describe-service-errors
  [--stack-id <value>]
  [--instance-id <value>]
  [--service-error-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ServiceErrors -> (list)

  

  An array of ``ServiceError`` objects that describe the specified service errors.

  

  (structure)

    

    Describes an AWS OpsWorks Stacks service error.

    

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

      

      

    

  

