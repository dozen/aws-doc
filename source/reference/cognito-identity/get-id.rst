[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-id:


******
get-id
******



===========
Description
===========



Generates (or retrieves) a Cognito ID. Supplying multiple logins will create an implicit linked account.

 

This is a public API. You do not need any credentials to call this API.



========
Synopsis
========

::

    get-id
  [--account-id <value>]
  --identity-pool-id <value>
  [--logins <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)
A standard AWS account ID (9+ digits).

``--identity-pool-id`` (string)
An identity pool ID in the format REGION:GUID.

``--logins`` (map)


  A set of optional name-value pairs that map provider names to provider tokens.

   

  The available provider names for ``Logins`` are as follows: 

   
  * Facebook: ``graph.facebook.com``  
   
  * Google: ``accounts.google.com``  
   
  * Amazon: ``www.amazon.com``  
   
  * Twitter: ``api.twitter.com``  
   
  * Digits: ``www.digits.com``  
   

   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityId -> (string)

  A unique identifier in the format REGION:GUID.

  

