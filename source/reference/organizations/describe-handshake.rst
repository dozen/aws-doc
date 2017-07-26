[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations describe-handshake:


******************
describe-handshake
******************



===========
Description
===========



Retrieves information about a previously requested handshake. The handshake ID comes from the response to the original  invite-account-to-organization operation that generated the handshake.

 

You can access handshakes that are ACCEPTED, DECLINED, or CANCELED for only 30 days after they change to that state. They are then deleted and no longer accessible.

 

This operation can be called from any account in the organization.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DescribeHandshake>`_


========
Synopsis
========

::

    describe-handshake
  --handshake-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--handshake-id`` (string)


  The unique identifier (ID) of the handshake that you want information about. You can get the ID from the original call to  invite-account-to-organization , or from a call to  list-handshakes-for-account or  list-handshakes-for-organization .

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for handshake ID string requires "h-" followed by from 8 to 32 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get details about a handshake**

The following example shows how to request details about a handshake.

Command::

  aws organizations describe-handshake --handshake-id h-examplehandshakeid111
  
Output::

  {
    "Handshake": {
      "Id": "h-examplehandshakeid111",
      "State": "OPEN",
      "Resources": [
        {
          "Type": "ORGANIZATION",
          "Value": "o-exampleorgid",
          "Resources": [
            {
              "Type": "MASTER_EMAIL",
              "Value": "bill@example.com"
            },
            {
              "Type": "MASTER_NAME",
              "Value": "Master Account"
            }
          ]
        },
        {
          "Type": "EMAIL",
          "Value": "anika@example.com"
        }
      ],
      "Parties": [
        {
          "Type": "ORGANIZATION",
          "Id": "o-exampleorgid"
        },
        {
          "Type": "EMAIL",
          "Id": "anika@example.com"
        }
      ],
      "Action": "INVITE",
      "RequestedTimestamp": 1470158698.046,
      "ExpirationTimestamp": 1471454698.046, 
      "Arn": "arn:aws:organizations::111111111111:handshake/o-exampleorgid/invite/h-examplehandshakeid111"
    }
  }

======
Output
======

Handshake -> (structure)

  

  A structure that contains information about the specified handshake.

  

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
             

            

            

          

        

      

    

  

