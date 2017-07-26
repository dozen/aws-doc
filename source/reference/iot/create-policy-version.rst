[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-policy-version:


*********************
create-policy-version
*********************



===========
Description
===========



Creates a new version of the specified AWS IoT policy. To update a policy, create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must delete an existing version using  delete-policy-version before you create a new version.

 

Optionally, you can set the new version as the policy's default version. The default version is the operative version; that is, the version that is in effect for the certificates that the policy is attached to.



========
Synopsis
========

::

    create-policy-version
  --policy-name <value>
  --policy-document <value>
  [--set-as-default | --no-set-as-default]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--policy-document`` (string)


  The JSON document that describes the policy. Minimum length of 1. Maximum length of 2048 excluding whitespaces

  

``--set-as-default`` | ``--no-set-as-default`` (boolean)


  Specifies whether the policy version is set as the default. When this parameter is true, the new policy version becomes the operative version; that is, the version that is in effect for the certificates that the policy is attached to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

