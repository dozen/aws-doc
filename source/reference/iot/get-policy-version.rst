[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-policy-version:


******************
get-policy-version
******************



===========
Description
===========



Gets information about the specified policy version.



========
Synopsis
========

::

    get-policy-version
  --policy-name <value>
  --policy-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy.

  

``--policy-version-id`` (string)


  The policy version ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policyArn -> (string)

  

  The policy ARN.

  

  

policyName -> (string)

  

  The policy name.

  

  

policyDocument -> (string)

  

  The JSON document that describes the policy.

  

  

policyVersionId -> (string)

  

  The policy version ID.

  

  

isDefaultVersion -> (boolean)

  

  Specifies whether the policy version is the default.

  

  

