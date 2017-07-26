[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-identity-policies:


*********************
get-identity-policies
*********************



===========
Description
===========



Returns the requested sending authorization policies for the given identity (email address or domain). The policies are returned as a map of policy names to policy contents. You can retrieve a maximum of 20 policies at a time.

 

.. note::

  This API is for the identity owner only. If you have not verified the identity, this API will return an error.

 

Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    get-identity-policies
  --identity <value>
  --policy-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity`` (string)


  The identity for which the policies will be retrieved. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

   

  To successfully call this API, you must own the identity.

  

``--policy-names`` (list)


  A list of the names of policies to be retrieved. You can retrieve a maximum of 20 policies at a time. If you do not know the names of the policies that are attached to the identity, you can use ``list-identity-policies`` .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Policies -> (map)

  

  A map of policy names to policies.

  

  key -> (string)

    

    

  value -> (string)

    

    

  



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization.html
