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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/GetId>`_


========
Synopsis
========

::

    get-id
  [--account-id <value>]
  --identity-pool-id <value>
  [--logins <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  A standard AWS account ID (9+ digits).

  

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--logins`` (map)


  A set of optional name-value pairs that map provider names to provider tokens. The available provider names for ``Logins`` are as follows:

   

   
  * Facebook: ``graph.facebook.com``   
   
  * Amazon Cognito Identity Provider: ``cognito-idp.us-east-1.amazonaws.com/us-east-1_123456789``   
   
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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID.

  

  

