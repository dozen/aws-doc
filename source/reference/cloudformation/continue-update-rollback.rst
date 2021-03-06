[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation continue-update-rollback:


************************
continue-update-rollback
************************



===========
Description
===========



For a specified stack that is in the ``UPDATE_ROLLBACK_FAILED`` state, continues rolling it back to the ``UPDATE_ROLLBACK_COMPLETE`` state. Depending on the cause of the failure, you can manually `fix the error <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/troubleshooting.html#troubleshooting-errors-update-rollback-failed>`_ and continue the rollback. By continuing the rollback, you can return your stack to a working state (the ``UPDATE_ROLLBACK_COMPLETE`` state), and then try to update the stack again.

 

A stack goes into the ``UPDATE_ROLLBACK_FAILED`` state when AWS CloudFormation cannot roll back all changes after a failed stack update. For example, you might have a stack that is rolling back to an old database instance that was deleted outside of AWS CloudFormation. Because AWS CloudFormation doesn't know the database was deleted, it assumes that the database instance still exists and attempts to roll back to it, causing the update rollback to fail.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ContinueUpdateRollback>`_


========
Synopsis
========

::

    continue-update-rollback
  --stack-name <value>
  [--role-arn <value>]
  [--resources-to-skip <value>]
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique ID of the stack that you want to continue rolling back.

   

  .. note::

     

    Don't specify the name of a nested stack (a stack that was created by using the ``AWS::CloudFormation::Stack`` resource). Instead, use this operation on the parent stack (the stack that contains the ``AWS::CloudFormation::Stack`` resource).

     

  

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of an AWS Identity and Access Management (IAM) role that AWS CloudFormation assumes to roll back the stack. AWS CloudFormation uses the role's credentials to make calls on your behalf. AWS CloudFormation always uses this role for all future operations on the stack. As long as users have permission to operate on the stack, AWS CloudFormation uses this role even if the users don't have permission to pass it. Ensure that the role grants least privilege.

   

  If you don't specify a value, AWS CloudFormation uses the role that was previously associated with the stack. If no role is available, AWS CloudFormation uses a temporary session that is generated from your user credentials.

  

``--resources-to-skip`` (list)


  A list of the logical IDs of the resources that AWS CloudFormation skips during the continue update rollback operation. You can specify only resources that are in the ``UPDATE_FAILED`` state because a rollback failed. You can't specify resources that are in the ``UPDATE_FAILED`` state for other reasons, for example, because an update was cancelled. To check why a resource update failed, use the  describe-stack-resources action, and view the resource status reason. 

   

  .. warning::

     

    Specify this property to skip rolling back resources that AWS CloudFormation can't successfully roll back. We recommend that you `troubleshoot <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/troubleshooting.html#troubleshooting-errors-update-rollback-failed>`_ resources before skipping them. AWS CloudFormation sets the status of the specified resources to ``UPDATE_COMPLETE`` and continues to roll back the stack. After the rollback is complete, the state of the skipped resources will be inconsistent with the state of the resources in the stack template. Before performing another stack update, you must update the stack or resources to be consistent with each other. If you don't, subsequent stack updates might fail, and the stack will become unrecoverable. 

     

   

  Specify the minimum number of resources required to successfully roll back your stack. For example, a failed resource update might cause dependent resources to fail. In this case, it might not be necessary to skip the dependent resources. 

   

  To skip resources that are part of nested stacks, use the following format: ``NestedStackName.ResourceLogicalID`` . If you want to specify the logical ID of a stack resource (``Type: AWS::CloudFormation::Stack`` ) in the ``resources-to-skip`` list, then its corresponding embedded stack must be in one of the following states: ``DELETE_IN_PROGRESS`` , ``DELETE_COMPLETE`` , or ``DELETE_FAILED`` . 

   

  .. note::

     

    Don't confuse a child stack's name with its corresponding logical ID defined in the parent stack. For an example of a continue update rollback operation with nested stacks, see `Using resources-to-skip to recover a nested stacks hierarchy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-continueupdaterollback.html#nested-stacks>`_ . 

     

  



Syntax::

  "string" "string" ...



``--client-request-token`` (string)


  A unique identifier for this ``continue-update-rollback`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to continue the rollback to a stack with the same name. You might retry ``continue-update-rollback`` requests to ensure that AWS CloudFormation successfully received them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

