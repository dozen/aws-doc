[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-context-keys-for-principal-policy:


*************************************
get-context-keys-for-principal-policy
*************************************



===========
Description
===========



Gets a list of all of the context keys referenced in ``Condition`` elements in all of the IAM policies attached to the specified IAM entity. The entity can be an IAM user, group, or role. If you specify a user, then the request also includes all of the policies attached to groups that the user is a member of.

 

You can optionally include a list of one or more additional policies, specified as strings. If you want to include only a list of policies by string, use  get-context-keys-for-custom-policy instead.

 

**Note:** This API discloses information about the permissions granted to other users. If you do not want users to see other user's permissions, then consider allowing them to use  get-context-keys-for-custom-policy instead.

 

Context keys are variables maintained by AWS and its services that provide details about the context of an API query request, and can be evaluated by using the ``Condition`` element of an IAM policy. Use get-context-keys-for-principal-policy to understand what key names and values you must supply when you call  simulate-principal-policy .



========
Synopsis
========

::

    get-context-keys-for-principal-policy
  --policy-source-arn <value>
  [--policy-input-list <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-source-arn`` (string)


  The ARN of a user, group, or role whose policies contain the context keys that you want listed. If you specify a user, the list includes context keys that are found in all policies attached to the user as well as to all groups that the user is a member of. If you pick a group or a role, then it includes only those context keys that are found in policies attached to that entity. Note that all parameters are shown in unencoded form here for clarity, but must be URL encoded to be included as a part of a real HTML request.

  

``--policy-input-list`` (list)


  A optional list of additional policies for which you want list of context keys used in ``Condition`` elements.

  



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

    

    

  

