[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-policy:


**********
get-policy
**********



===========
Description
===========



Gets information about the specified policy with the policy document of the default version.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/GetPolicy>`_


========
Synopsis
========

::

    get-policy
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

