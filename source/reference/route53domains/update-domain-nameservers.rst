[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains update-domain-nameservers:


*************************
update-domain-nameservers
*************************



===========
Description
===========



This operation replaces the current set of name servers for the domain with the specified set of name servers. If you use Amazon Route 53 as your DNS service, specify the four name servers in the delegation set for the hosted zone for the domain. 

 

If successful, this operation returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.



========
Synopsis
========

::

    update-domain-nameservers
  --domain-name <value>
  [--fi-auth-key <value>]
  --nameservers <value>
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

  

``--fi-auth-key`` (string)


  The authorization key for .fi domains

  

``--nameservers`` (list)


  A list of new name servers for the domain.

   

  Type: Complex

   

  Children: ``Name`` , ``GlueIps`` 

   

  Required: Yes

  



Shorthand Syntax::

    Name=string,GlueIps=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "GlueIps": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

OperationId -> (string)

  

  Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

   

  Type: String

   

  Default: None

   

  Constraints: Maximum 255 characters.

  

  

