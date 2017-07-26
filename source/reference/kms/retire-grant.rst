[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms retire-grant:


************
retire-grant
************



===========
Description
===========



Retires a grant. To clean up, you can retire a grant when you're done using it. You should revoke a grant when you intend to actively deny operations that depend on it. The following are permitted to call this API:

 

 
* The AWS account (root user) under which the grant was created 
 
* The ``RetiringPrincipal`` , if present in the grant 
 
* The ``GranteePrincipal`` , if ``retire-grant`` is an operation specified in the grant 
 

 

You must identify the grant to retire by its grant token or by a combination of the grant ID and the Amazon Resource Name (ARN) of the customer master key (CMK). A grant token is a unique variable-length base64-encoded string. A grant ID is a 64 character unique identifier of a grant. The  create-grant operation returns both.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/RetireGrant>`_


========
Synopsis
========

::

    retire-grant
  [--grant-token <value>]
  [--key-id <value>]
  [--grant-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--grant-token`` (string)


  Token that identifies the grant to be retired.

  

``--key-id`` (string)


  The Amazon Resource Name of the CMK associated with the grant. Example:

   

   
  * arn:aws:kms:us-east-2:444455556666:key/1234abcd-12ab-34cd-56ef-1234567890ab 
   

  

``--grant-id`` (string)


  Unique identifier of the grant to retire. The grant ID is returned in the response to a ``create-grant`` operation.

   

   
  * Grant ID Example - 0123456789012345678901234567890123456789012345678901234567890123 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None