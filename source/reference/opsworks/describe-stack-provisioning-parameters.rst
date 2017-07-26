[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-stack-provisioning-parameters:


**************************************
describe-stack-provisioning-parameters
**************************************



===========
Description
===========



Requests a description of a stack's provisioning parameters.

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-stack-provisioning-parameters
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AgentInstallerUrl -> (string)

  

  The AWS OpsWorks agent installer's URL.

  

  

Parameters -> (map)

  

  An embedded object that contains the provisioning parameters.

  

  key -> (string)

    

    

  value -> (string)

    

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
