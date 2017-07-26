[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity lookup-developer-identity:


*************************
lookup-developer-identity
*************************



===========
Description
===========



Retrieves the ``IdentityID`` associated with a ``developer-user-identifier`` or the list of ``developer-user-identifier`` s associated with an ``identity-id`` for an existing identity. Either ``IdentityID`` or ``developer-user-identifier`` must not be null. If you supply only one of these values, the other value will be searched in the database and returned as a part of the response. If you supply both, ``developer-user-identifier`` will be matched against ``IdentityID`` . If the values are verified against the database, the response returns both values and is the same as the request. Otherwise a ``ResourceConflictException`` is thrown.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/LookupDeveloperIdentity>`_


========
Synopsis
========

::

    lookup-developer-identity
  --identity-pool-id <value>
  [--identity-id <value>]
  [--developer-user-identifier <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--developer-user-identifier`` (string)


  A unique ID used by your backend authentication process to identify a user. Typically, a developer identity provider would issue many developer user identifiers, in keeping with the number of users.

  

``--max-results`` (integer)


  The maximum number of identities to return.

  

``--next-token`` (string)


  A pagination token. The first call you make will have ``NextToken`` set to null. After that the service will return ``NextToken`` values as needed. For example, let's say you make a request with ``MaxResults`` set to 10, and there are 20 matches in the database. The service will return a pagination token as a part of the response. This token can be used to call the API again and get results starting from the 11th match.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID.

  

  

DeveloperUserIdentifierList -> (list)

  

  This is the list of developer user identifiers associated with an identity ID. Cognito supports the association of multiple developer user identifiers with an identity ID.

  

  (string)

    

    

  

NextToken -> (string)

  

  A pagination token. The first call you make will have ``NextToken`` set to null. After that the service will return ``NextToken`` values as needed. For example, let's say you make a request with ``MaxResults`` set to 10, and there are 20 matches in the database. The service will return a pagination token as a part of the response. This token can be used to call the API again and get results starting from the 11th match.

  

  

