[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-context-keys-for-custom-policy:


**********************************
get-context-keys-for-custom-policy
**********************************



===========
Description
===========



Gets a list of all of the context keys referenced in ``Condition`` elements in the input policies. The policies are supplied as a list of one or more strings. To get the context keys from policies associated with an IAM user, group, or role, use  get-context-keys-for-principal-policy .

 

Context keys are variables maintained by AWS and its services that provide details about the context of an API query request, and can be evaluated by using the ``Condition`` element of an IAM policy. Use get-context-keys-for-custom-policy to understand what key names and values you must supply when you call  simulate-custom-policy . Note that all parameters are shown in unencoded form here for clarity, but must be URL encoded to be included as a part of a real HTML request.



========
Synopsis
========

::

    get-context-keys-for-custom-policy
  --policy-input-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-input-list`` (list)


  A list of policies for which you want list of context keys used in ``Condition`` elements. Each document is specified as a string containing the complete, valid JSON text of an IAM policy.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ContextKeyNames -> (list)

  

  The list of context keys that are used in the ``Condition`` elements of the input policies.

  

  (string)

    

    

  

