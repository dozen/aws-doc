[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp list-user-pool-clients:


**********************
list-user-pool-clients
**********************



===========
Description
===========



Lists the clients that have been created for the specified user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ListUserPoolClients>`_


========
Synopsis
========

::

    list-user-pool-clients
  --user-pool-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to list user pool clients.

  

``--max-results`` (integer)


  The maximum number of results you want the request to return when listing the user pool clients.

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserPoolClients -> (list)

  

  The user pool clients in the response that lists user pool clients.

  

  (structure)

    

    The description of the user pool client.

    

    ClientId -> (string)

      

      The ID of the client associated with the user pool.

      

      

    UserPoolId -> (string)

      

      The user pool ID for the user pool where you want to describe the user pool client.

      

      

    ClientName -> (string)

      

      The client name from the user pool client description.

      

      

    

  

NextToken -> (string)

  

  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

  

