[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-context-keys-for-custom-policy:


**********************************
get-context-keys-for-custom-policy
**********************************



===========
Description
===========



Gets a list of all of the context keys referenced in the input policies. The policies are supplied as a list of one or more strings. To get the context keys from policies associated with an IAM user, group, or role, use  get-context-keys-for-principal-policy .

 

Context keys are variables maintained by AWS and its services that provide details about the context of an API query request, and can be evaluated by testing against a value specified in an IAM policy. Use get-context-keys-for-custom-policy to understand what key names and values you must supply when you call  simulate-custom-policy . Note that all parameters are shown in unencoded form here for clarity, but must be URL encoded to be included as a part of a real HTML request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetContextKeysForCustomPolicy>`_


========
Synopsis
========

::

    get-context-keys-for-custom-policy
  --policy-input-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-input-list`` (list)


  A list of policies for which you want the list of context keys referenced in those policies. Each document is specified as a string containing the complete, valid JSON text of an IAM policy.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ContextKeyNames -> (list)

  

  The list of context keys that are referenced in the input policies.

  

  (string)

    

    

  

