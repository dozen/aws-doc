[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms create-key:


**********
create-key
**********



===========
Description
===========



Creates a customer master key (CMK).

 

You can use a CMK to encrypt small amounts of data (4 KiB or less) directly, but CMKs are more commonly used to encrypt data encryption keys (DEKs), which are used to encrypt raw data. For more information about DEKs and the difference between CMKs and DEKs, see the following:

 

 
* The  generate-data-key operation 
 
* `AWS Key Management Service Concepts <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html>`_ in the *AWS Key Management Service Developer Guide*   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/CreateKey>`_


========
Synopsis
========

::

    create-key
  [--policy <value>]
  [--description <value>]
  [--key-usage <value>]
  [--origin <value>]
  [--bypass-policy-lockout-safety-check | --no-bypass-policy-lockout-safety-check]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy`` (string)


  The key policy to attach to the CMK.

   

  If you specify a policy and do not set ``BypassPolicyLockoutSafetyCheck`` to true, the policy must meet the following criteria:

   

   
  * It must allow the principal that is making the ``create-key`` request to make a subsequent  put-key-policy request on the CMK. This reduces the likelihood that the CMK becomes unmanageable. For more information, refer to the scenario in the `Default Key Policy <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default-allow-root-enable-iam>`_ section in the *AWS Key Management Service Developer Guide* . 
   
  * The principals that are specified in the key policy must exist and be visible to AWS KMS. When you create a new AWS principal (for example, an IAM user or role), you might need to enforce a delay before specifying the new principal in a key policy because the new principal might not immediately be visible to AWS KMS. For more information, see `Changes that I make are not always immediately visible <http://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_general.html#troubleshoot_general_eventual-consistency>`_ in the *IAM User Guide* . 
   

   

  If you do not specify a policy, AWS KMS attaches a default key policy to the CMK. For more information, see `Default Key Policy <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default>`_ in the *AWS Key Management Service Developer Guide* .

   

  The policy size limit is 32 KiB (32768 bytes).

  

``--description`` (string)


  A description of the CMK.

   

  Use a description that helps you decide whether the CMK is appropriate for a task.

  

``--key-usage`` (string)


  The intended use of the CMK.

   

  You can use CMKs only for symmetric encryption and decryption.

  

  Possible values:

  
  *   ``ENCRYPT_DECRYPT``

  

  

``--origin`` (string)


  The source of the CMK's key material.

   

  The default is ``AWS_KMS`` , which means AWS KMS creates the key material. When this parameter is set to ``EXTERNAL`` , the request creates a CMK without key material so that you can import key material from your existing key management infrastructure. For more information about importing key material into AWS KMS, see `Importing Key Material <http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys.html>`_ in the *AWS Key Management Service Developer Guide* .

   

  The CMK's ``Origin`` is immutable and is set when the CMK is created.

  

  Possible values:

  
  *   ``AWS_KMS``

  
  *   ``EXTERNAL``

  

  

``--bypass-policy-lockout-safety-check`` | ``--no-bypass-policy-lockout-safety-check`` (boolean)


  A flag to indicate whether to bypass the key policy lockout safety check.

   

  .. warning::

     

    Setting this value to true increases the likelihood that the CMK becomes unmanageable. Do not set this value to true indiscriminately.

     

    For more information, refer to the scenario in the `Default Key Policy <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default-allow-root-enable-iam>`_ section in the *AWS Key Management Service Developer Guide* .

     

   

  Use this parameter only when you include a policy in the request and you intend to prevent the principal that is making the request from making a subsequent  put-key-policy request on the CMK.

   

  The default value is false.

  

``--tags`` (list)


  One or more tags. Each tag consists of a tag key and a tag value. Tag keys and tag values are both required, but tag values can be empty (null) strings.

   

  Use this parameter to tag the CMK when it is created. Alternately, you can omit this parameter and instead tag the CMK after it is created using  tag-resource .

  



Shorthand Syntax::

    TagKey=string,TagValue=string ...




JSON Syntax::

  [
    {
      "TagKey": "string",
      "TagValue": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

KeyMetadata -> (structure)

  

  Metadata associated with the CMK.

  

  AWSAccountId -> (string)

    

    The twelve-digit account ID of the AWS account that owns the CMK.

    

    

  KeyId -> (string)

    

    The globally unique identifier for the CMK.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the CMK. For examples, see `AWS Key Management Service (AWS KMS) <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-kms>`_ in the Example ARNs section of the *AWS General Reference* .

    

    

  CreationDate -> (timestamp)

    

    The date and time when the CMK was created.

    

    

  Enabled -> (boolean)

    

    Specifies whether the CMK is enabled. When ``KeyState`` is ``Enabled`` this value is true, otherwise it is false.

    

    

  Description -> (string)

    

    The description of the CMK.

    

    

  KeyUsage -> (string)

    

    The cryptographic operations for which you can use the CMK. Currently the only allowed value is ``ENCRYPT_DECRYPT`` , which means you can use the CMK for the  encrypt and  decrypt operations.

    

    

  KeyState -> (string)

    

    The state of the CMK.

     

    For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key <http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html>`_ in the *AWS Key Management Service Developer Guide* .

    

    

  DeletionDate -> (timestamp)

    

    The date and time after which AWS KMS deletes the CMK. This value is present only when ``KeyState`` is ``PendingDeletion`` , otherwise this value is omitted.

    

    

  ValidTo -> (timestamp)

    

    The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. This value is present only for CMKs whose ``Origin`` is ``EXTERNAL`` and whose ``ExpirationModel`` is ``KEY_MATERIAL_EXPIRES`` , otherwise this value is omitted.

    

    

  Origin -> (string)

    

    The source of the CMK's key material. When this value is ``AWS_KMS`` , AWS KMS created the key material. When this value is ``EXTERNAL`` , the key material was imported from your existing key management infrastructure or the CMK lacks key material.

    

    

  ExpirationModel -> (string)

    

    Specifies whether the CMK's key material expires. This value is present only when ``Origin`` is ``EXTERNAL`` , otherwise this value is omitted.

    

    

  KeyManager -> (string)

    

    The CMK's manager. CMKs are either customer-managed or AWS-managed. For more information about the difference, see `Customer Master Keys <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#master_keys>`_ in the *AWS Key Management Service Developer Guide* .

    

    

  

