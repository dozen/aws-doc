[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms put-key-policy:


**************
put-key-policy
**************



===========
Description
===========



Attaches a key policy to the specified customer master key (CMK).

 

For more information about key policies, see `Key Policies <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html>`_ in the *AWS Key Management Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/PutKeyPolicy>`_


========
Synopsis
========

::

    put-key-policy
  --key-id <value>
  --policy-name <value>
  --policy <value>
  [--bypass-policy-lockout-safety-check | --no-bypass-policy-lockout-safety-check]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the CMK.

   

  Use the CMK's unique identifier or its Amazon Resource Name (ARN). For example:

   

   
  * Unique ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
   
  * ARN: arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
   

  

``--policy-name`` (string)


  The name of the key policy.

   

  This value must be ``default`` .

  

``--policy`` (string)


  The key policy to attach to the CMK.

   

  If you do not set ``BypassPolicyLockoutSafetyCheck`` to true, the policy must meet the following criteria:

   

   
  * It must allow the principal that is making the ``put-key-policy`` request to make a subsequent ``put-key-policy`` request on the CMK. This reduces the likelihood that the CMK becomes unmanageable. For more information, refer to the scenario in the `Default Key Policy <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default-allow-root-enable-iam>`_ section in the *AWS Key Management Service Developer Guide* . 
   
  * The principals that are specified in the key policy must exist and be visible to AWS KMS. When you create a new AWS principal (for example, an IAM user or role), you might need to enforce a delay before specifying the new principal in a key policy because the new principal might not immediately be visible to AWS KMS. For more information, see `Changes that I make are not always immediately visible <http://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_general.html#troubleshoot_general_eventual-consistency>`_ in the *IAM User Guide* . 
   

   

  The policy size limit is 32 KiB (32768 bytes).

  

``--bypass-policy-lockout-safety-check`` | ``--no-bypass-policy-lockout-safety-check`` (boolean)


  A flag to indicate whether to bypass the key policy lockout safety check.

   

  .. warning::

     

    Setting this value to true increases the likelihood that the CMK becomes unmanageable. Do not set this value to true indiscriminately.

     

    For more information, refer to the scenario in the `Default Key Policy <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default-allow-root-enable-iam>`_ section in the *AWS Key Management Service Developer Guide* .

     

   

  Use this parameter only when you intend to prevent the principal that is making the request from making a subsequent ``put-key-policy`` request on the CMK.

   

  The default value is false.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None