[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-policy-version:


******************
get-policy-version
******************



===========
Description
===========



Gets information about the specified policy version.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/GetPolicyVersion>`_


========
Synopsis
========

::

    get-policy-version
  --policy-name <value>
  --policy-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy.

  

``--policy-version-id`` (string)


  The policy version ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

