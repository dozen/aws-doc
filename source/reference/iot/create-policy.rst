[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-policy:


*************
create-policy
*************



===========
Description
===========



Creates an AWS IoT policy.

 

The created policy is the default version for the policy. This operation creates a policy version with a version identifier of **1** and sets **1** as the policy's default version.



========
Synopsis
========

::

    create-policy
  --policy-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--policy-document`` (string)


  The JSON document that describes the policy. The length of the **policyDocument** must be a minimum length of 1, with a maximum length of 2048, excluding whitespace.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policyName -> (string)

  

  The policy name.

  

  

policyArn -> (string)

  

  The policy ARN.

  

  

policyDocument -> (string)

  

  The JSON document that describes the policy.

  

  

policyVersionId -> (string)

  

  The policy version ID.

  

  

