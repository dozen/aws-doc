[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses delete-identity-policy:


**********************
delete-identity-policy
**********************



===========
Description
===========



Deletes the specified sending authorization policy for the given identity (email address or domain). This API returns successfully even if a policy with the specified name does not exist.

 

.. note::

  This API is for the identity owner only. If you have not verified the identity, this API will return an error.

 

Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    delete-identity-policy
  --identity <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity`` (string)


  The identity that is associated with the policy that you want to delete. You can specify the identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

   

  To successfully call this API, you must own the identity.

  

``--policy-name`` (string)


  The name of the policy to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization.html
