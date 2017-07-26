[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream describe-sessions:


*****************
describe-sessions
*****************



===========
Description
===========



Describes the streaming sessions for a stack and a fleet. If a user ID is provided, this operation returns streaming sessions for only that user. To retrieve the next set of items, pass this value for the ``nextToken`` parameter in a subsequent call to this operation. If an authentication type is not provided, the operation defaults to users authenticated using a streaming URL.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/DescribeSessions>`_


========
Synopsis
========

::

    describe-sessions
  --stack-name <value>
  --fleet-name <value>
  [--user-id <value>]
  [--next-token <value>]
  [--limit <value>]
  [--authentication-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name of the stack for which to list sessions.

  

``--fleet-name`` (string)


  The name of the fleet for which to list sessions.

  

``--user-id`` (string)


  The user for whom to list sessions. Use null to describe all the sessions for the stack and fleet.

  

``--next-token`` (string)


  The pagination token to use to retrieve the next page of results for this operation. If this value is null, it retrieves the first page.

  

``--limit`` (integer)


  The size of each page of results. The default value is 20 and the maximum supported value is 50.

  

``--authentication-type`` (string)


  The authentication method of the user. It can be ``API`` for a user authenticated using a streaming URL, or ``SAML`` for a SAML federated user. If an authentication type is not provided, the operation defaults to users authenticated using a streaming URL.

  

  Possible values:

  
  *   ``API``

  
  *   ``SAML``

  
  *   ``USERPOOL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Sessions -> (list)

  

  The list of streaming sessions.

  

  (structure)

    

    Contains the parameters for a streaming session.

    

    Id -> (string)

      

      The unique ID for a streaming session.

      

      

    UserId -> (string)

      

      The identifier of the user for whom the session was created.

      

      

    StackName -> (string)

      

      The name of the stack for which the streaming session was created.

      

      

    FleetName -> (string)

      

      The name of the fleet for which the streaming session was created.

      

      

    State -> (string)

      

      The current state of the streaming session.

      

      

    AuthenticationType -> (string)

      

      The authentication method of the user for whom the session was created. It can be ``API`` for a user authenticated using a streaming URL or ``SAML`` for a SAML federated user.

      

      

    

  

NextToken -> (string)

  

  The pagination token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

