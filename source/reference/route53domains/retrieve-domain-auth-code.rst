[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains retrieve-domain-auth-code:


*************************
retrieve-domain-auth-code
*************************



===========
Description
===========



This operation returns the AuthCode for the domain. To transfer a domain to another registrar, you provide this value to the new registrar.



========
Synopsis
========

::

    retrieve-domain-auth-code
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

   

  Required: Yes

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AuthCode -> (string)

  

  The authorization code for the domain.

   

  Type: String

  

  

