[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-policy-version:


*********************
create-policy-version
*********************



===========
Description
===========



Creates a new version of the specified AWS IoT policy. To update a policy, create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must use  delete-policy-version to delete an existing version before you create a new one.

 

Optionally, you can set the new version as the policy's default version. The default version is the operative version (that is, the version that is in effect for the certificates to which the policy is attached).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreatePolicyVersion>`_


========
Synopsis
========

::

    create-policy-version
  --policy-name <value>
  --policy-document <value>
  [--set-as-default | --no-set-as-default]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--policy-document`` (string)


  The JSON document that describes the policy. Minimum length of 1. Maximum length of 2048, excluding whitespaces

  

``--set-as-default`` | ``--no-set-as-default`` (boolean)


  Specifies whether the policy version is set as the default. When this parameter is true, the new policy version becomes the operative version (that is, the version that is in effect for the certificates to which the policy is attached).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

policyArn -> (string)

  

  The policy ARN.

  

  

policyDocument -> (string)

  

  The JSON document that describes the policy.

  

  

policyVersionId -> (string)

  

  The policy version ID.

  

  

isDefaultVersion -> (boolean)

  

  Specifies whether the policy version is the default.

  

  

