[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses put-identity-policy:


*******************
put-identity-policy
*******************



===========
Description
===========



Adds or updates a sending authorization policy for the specified identity (an email address or a domain).

 

.. note::

   

  This API is for the identity owner only. If you have not verified the identity, this API will return an error.

   

 

Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/PutIdentityPolicy>`_


========
Synopsis
========

::

    put-identity-policy
  --identity <value>
  --policy-name <value>
  --policy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity`` (string)


  The identity to which the policy will apply. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

   

  To successfully call this API, you must own the identity.

  

``--policy-name`` (string)


  The name of the policy.

   

  The policy name cannot exceed 64 characters and can only include alphanumeric characters, dashes, and underscores.

  

``--policy`` (string)


  The text of the policy in JSON format. The policy cannot exceed 4 KB.

   

  For information about the syntax of sending authorization policies, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization-policies.html>`_ . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

