[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-policy:


**********
get-policy
**********



===========
Description
===========



Gets information about the specified policy with the policy document of the default version.



========
Synopsis
========

::

    get-policy
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy.

  

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

  

  

defaultVersionId -> (string)

  

  The default policy version ID.

  

  

