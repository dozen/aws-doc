[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-stack-provisioning-parameters:


**************************************
describe-stack-provisioning-parameters
**************************************



===========
Description
===========



Requests a description of a stack's provisioning parameters.

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeStackProvisioningParameters>`_


========
Synopsis
========

::

    describe-stack-provisioning-parameters
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AgentInstallerUrl -> (string)

  

  The AWS OpsWorks Stacks agent installer's URL.

  

  

Parameters -> (map)

  

  An embedded object that contains the provisioning parameters.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

