[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation delete-stack-instances:


**********************
delete-stack-instances
**********************



===========
Description
===========



Deletes stack instances for the specified accounts, in the specified regions. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DeleteStackInstances>`_


========
Synopsis
========

::

    delete-stack-instances
  --stack-set-name <value>
  --accounts <value>
  --regions <value>
  [--operation-preferences <value>]
  --retain-stacks | --no-retain-stacks
  [--operation-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you want to delete stack instances for.

  

``--accounts`` (list)


  The names of the AWS accounts that you want to delete stack instances for.

  



Syntax::

  "string" "string" ...



``--regions`` (list)


  The regions where you want to delete stack set instances. 

  



Syntax::

  "string" "string" ...



``--operation-preferences`` (structure)


  Preferences for how AWS CloudFormation performs this stack set operation.

  



Shorthand Syntax::

    RegionOrder=string,string,FailureToleranceCount=integer,FailureTolerancePercentage=integer,MaxConcurrentCount=integer,MaxConcurrentPercentage=integer




JSON Syntax::

  {
    "RegionOrder": ["string", ...],
    "FailureToleranceCount": integer,
    "FailureTolerancePercentage": integer,
    "MaxConcurrentCount": integer,
    "MaxConcurrentPercentage": integer
  }



``--retain-stacks`` | ``--no-retain-stacks`` (boolean)


  Removes the stack instances from the specified stack set, but doesn't delete the stacks. You can't reassociate a retained stack or add an existing, saved stack to a new stack set.

  

``--operation-id`` (string)


  The unique identifier for this stack set operation. 

   

  If you don't specify an operation ID, the SDK generates one automatically. 

   

  The operation ID also functions as an idempotency token, to ensure that AWS CloudFormation performs the stack set operation only once, even if you retry the request multiple times. You can retry stack set operation requests to ensure that AWS CloudFormation successfully received them.

   

  Repeating this stack set operation with a new operation ID retries all stack instances whose status is ``OUTDATED`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OperationId -> (string)

  

  The unique identifier for this stack set operation.

  

  

