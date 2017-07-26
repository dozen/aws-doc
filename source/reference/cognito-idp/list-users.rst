[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp list-users:


**********
list-users
**********



===========
Description
===========



Lists the users in the Amazon Cognito user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ListUsers>`_


========
Synopsis
========

::

    list-users
  --user-pool-id <value>
  [--attributes-to-get <value>]
  [--limit <value>]
  [--pagination-token <value>]
  [--filter <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool on which the search should be performed.

  

``--attributes-to-get`` (list)


  An array of strings, where each string is the name of a user attribute to be returned for each user in the search results. If the array is empty, all attributes are returned.

  



Syntax::

  "string" "string" ...



``--limit`` (integer)


  Maximum number of users to be returned.

  

``--pagination-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--filter`` (string)


  A filter string of the form "*AttributeName*  *Filter-Type* "*AttributeValue* "". Quotation marks within the filter string must be escaped using the backslash (\) character. For example, "``family_name`` = \"Reddy\"".

   

   
  * *AttributeName* : The name of the attribute to search for. You can only search for one attribute at a time. 
   
  * *Filter-Type* : For an exact match, use =, for example, "``given_name`` = \"Jon\"". For a prefix ("starts with") match, use ^=, for example, "``given_name`` ^= \"Jon\"".  
   
  * *AttributeValue* : The attribute value that must be matched for each user. 
   

   

  If the filter string is empty, ``list-users`` returns all users in the user pool.

   

  You can only search for the following standard attributes:

   

   
  * ``username`` (case-sensitive) 
   
  * ``email``   
   
  * ``phone_number``   
   
  * ``name``   
   
  * ``given_name``   
   
  * ``family_name``   
   
  * ``preferred_username``   
   
  * ``cognito:user_status`` (called **Enabled** in the Console) (case-sensitive) 
   
  * ``status`` (case-insensitive) 
   

   

  Custom attributes are not searchable.

   

  For more information, see `Searching for Users Using the list-users API <http://docs.aws.amazon.com/cognito/latest/developerguide/how-to-manage-user-accounts.html#cognito-user-pools-searching-for-users-using-listusers-api>`_ and `Examples of Using the list-users API <http://docs.aws.amazon.com/cognito/latest/developerguide/how-to-manage-user-accounts.html#cognito-user-pools-searching-for-users-listusers-api-examples>`_ in the *Amazon Cognito Developer Guide* .

  

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

          

          

        

      

    

  

PaginationToken -> (string)

  

  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

  

