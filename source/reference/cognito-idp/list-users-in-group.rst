[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp list-users-in-group:


*******************
list-users-in-group
*******************



===========
Description
===========



Lists the users in the specified group.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ListUsersInGroup>`_


========
Synopsis
========

::

    list-users-in-group
  --user-pool-id <value>
  --group-name <value>
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool.

  

``--group-name`` (string)


  The name of the group.

  

``--limit`` (integer)


  The limit of the request to list users.

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Users -> (list)

  

  The users returned in the request to list users.

  

  (structure)

    

    The user type.

    

    Username -> (string)

      

      The user name of the user you wish to describe.

      

      

    Attributes -> (list)

      

      A container with information about the user type attributes.

      

      (structure)

        

        Specifies whether the attribute is standard or custom.

        

        Name -> (string)

          

          The name of the attribute.

          

          

        Value -> (string)

          

          The value of the attribute.

          

          

        

      

    UserCreateDate -> (timestamp)

      

      The creation date of the user.

      

      

    UserLastModifiedDate -> (timestamp)

      

      The last modified date of the user.

      

      

    Enabled -> (boolean)

      

      Specifies whether the user is enabled.

      

      

    UserStatus -> (string)

      

      The user status. Can be one of the following:

       

       
      * UNCONFIRMED - User has been created but not confirmed. 
       
      * CONFIRMED - User has been confirmed. 
       
      * ARCHIVED - User is no longer active. 
       
      * COMPROMISED - User is disabled due to a potential security threat. 
       
      * UNKNOWN - User status is not known. 
       

      

      

    MFAOptions -> (list)

      

      The MFA options for the user.

      

      (structure)

        

        Specifies the different settings for multi-factor authentication (MFA).

        

        DeliveryMedium -> (string)

          

          The delivery medium (email message or SMS message) to send the MFA code.

          

          

        AttributeName -> (string)

          

          The attribute name of the MFA option type.

          

          

        

      

    

  

NextToken -> (string)

  

  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

  

