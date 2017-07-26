[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations accept-handshake:


****************
accept-handshake
****************



===========
Description
===========



Sends a response to the originator of a handshake agreeing to the action proposed by the handshake request. 

 

This operation can be called only by the following principals when they also have the relevant IAM permissions:

 

 
* **Invitation to join** or **Approve all features request** handshakes: only a principal from the member account.  
 
* **Enable all features final confirmation** handshake: only a principal from the master account. For more information about invitations, see `Inviting an AWS Account to Join Your Organization <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_invites.html>`_ in the *AWS Organizations User Guide* . For more information about requests to enable all features in the organization, see `Enabling All Features in Your Organization <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html>`_ in the *AWS Organizations User Guide* . 
 

 

After you accept a handshake, it continues to appear in the results of relevant APIs for only 30 days. After that it is deleted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/AcceptHandshake>`_


========
Synopsis
========

::

    accept-handshake
  --handshake-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--handshake-id`` (string)


  The unique identifier (ID) of the handshake that you want to accept.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for handshake ID string requires "h-" followed by from 8 to 32 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To accept a handshake**

Bill, the owner of an organization, has previously invited Juan's account to join his organization. The following example shows Juan's account accepting the handshake and thus agreeing to the invitation.

Command::

  aws organizations accept-handshake --handshake-id h-examplehandshakeid111

The output displays that the handshake is now in the ACCEPTED state.

Output::

  {
    "Handshake": {
      "Action": "INVITE",
      "Arn": "arn:aws:organizations::111111111111:handshake/o-exampleorgid/invite/h-examplehandshakeid111",
      "RequestedTimestamp": 1481656459.257,
      "ExpirationTimestamp": 1482952459.257,
      "Id": "h-examplehandshakeid111",
      "Parties": [
        {
          "Id": "o-exampleorgid",
          "Type": "ORGANIZATION"
        },
        {
          "Id": "juan@example.com",
          "Type": "EMAIL"
        }
      ],
      "Resources": [
        {
          "Resources": [
            {
              "Type": "MASTER_EMAIL",
              "Value": "bill@amazon.com"
            },
            {
              "Type": "MASTER_NAME",
              "Value": "Org Master Account"
            },
            {
              "Type": "ORGANIZATION_FEATURE_SET",
              "Value": "ALL"
            }
          ],
          "Type": "ORGANIZATION",
          "Value": "o-exampleorgid"
        },
        {
          "Type": "EMAIL",
          "Value": "juan@example.com"
        }
      ],
      "State": "ACCEPTED"
    }
  }

======
Output
======

Handshake -> (structure)

  

  A structure that contains details about the accepted handshake.

  

  Id -> (string)

    

    The unique identifier (ID) of a handshake. The originating account creates the ID when it initiates the handshake.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for handshake ID string requires "h-" followed by from 8 to 32 lower-case letters or digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of a handshake.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  Parties -> (list)

    

    Information about the two accounts that are participating in the handshake.

    

    (structure)

      

      Identifies a participant in a handshake.

      

      Id -> (string)

        

        The unique identifier (ID) for the party.

         

        The `regex pattern <http://wikipedia.org/wiki/regex>`_ for handshake ID string requires "h-" followed by from 8 to 32 lower-case letters or digits.

        

        

      Type -> (string)

        

        The type of party.

        

        

      

    

  State -> (string)

    

    The current state of the handshake. Use the state to trace the flow of the handshake through the process from its creation to its acceptance. The meaning of each of the valid values is as follows:

     

     
    * **REQUESTED** : This handshake was sent to multiple recipients (applicable to only some handshake types) and not all recipients have responded yet. The request stays in this state until all recipients respond. 
     
    * **OPEN** : This handshake was sent to multiple recipients (applicable to only some policy types) and all recipients have responded, allowing the originator to complete the handshake action. 
     
    * **CANCELED** : This handshake is no longer active because it was canceled by the originating account. 
     
    * **ACCEPTED** : This handshake is complete because it has been accepted by the recipient. 
     
    * **DECLINED** : This handshake is no longer active because it was declined by the recipient account. 
     
    * **EXPIRED** : This handshake is no longer active because the originator did not receive a response of any kind from the recipient before the expiration time (15 days). 
     

    

    

  RequestedTimestamp -> (timestamp)

    

    The date and time that the handshake request was made.

    

    

  ExpirationTimestamp -> (timestamp)

    

    The date and time that the handshake expires. If the recipient of the handshake request fails to respond before the specified date and time, the handshake becomes inactive and is no longer valid.

    

    

  Action -> (string)

    

    The type of handshake, indicating what action occurs when the recipient accepts the handshake.

    

    

  Resources -> (list)

    

    Additional information that is needed to process the handshake.

    

    (structure)

      

      Contains additional data that is needed to process a handshake.

      

      Value -> (string)

        

        The information that is passed to the other party in the handshake. The format of the value string must match the requirements of the specified type.

        

        

      Type -> (string)

        

        The type of information being passed, specifying how the value is to be interpreted by the other party:

         

         
        * ``ACCOUNT`` - Specifies an AWS account ID number. 
         
        * ``ORGANIZATION`` - Specifies an organization ID number. 
         
        * ``EMAIL`` - Specifies the email address that is associated with the account that receives the handshake.  
         
        * ``OWNER_EMAIL`` - Specifies the email address associated with the master account. Included as information about an organization.  
         
        * ``OWNER_NAME`` - Specifies the name associated with the master account. Included as information about an organization.  
         
        * ``NOTES`` - Additional text provided by the handshake initiator and intended for the recipient to read. 
         

        

        

      Resources -> (list)

        

        When needed, contains an additional array of ``HandshakeResource`` objects.

        

        (structure)

          

          Contains additional data that is needed to process a handshake.

          

          Value -> (string)

            

            The information that is passed to the other party in the handshake. The format of the value string must match the requirements of the specified type.

            

            

          Type -> (string)

            

            The type of information being passed, specifying how the value is to be interpreted by the other party:

             

             
            * ``ACCOUNT`` - Specifies an AWS account ID number. 
             
            * ``ORGANIZATION`` - Specifies an organization ID number. 
             
            * ``EMAIL`` - Specifies the email address that is associated with the account that receives the handshake.  
             
            * ``OWNER_EMAIL`` - Specifies the email address associated with the master account. Included as information about an organization.  
             
            * ``OWNER_NAME`` - Specifies the name associated with the master account. Included as information about an organization.  
             
            * ``NOTES`` - Additional text provided by the handshake initiator and intended for the recipient to read. 
             

            

            

          

        

      

    

  

