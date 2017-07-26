[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations enable-all-features:


*******************
enable-all-features
*******************



===========
Description
===========



Enables all features in an organization. This enables the use of organization policies that can restrict the services and actions that can be called in each account. Until you enable all features, you have access only to consolidated billing, and you can't use any of the advanced account administration features that AWS Organizations supports. For more information, see `Enabling All Features in Your Organization <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html>`_ in the *AWS Organizations User Guide* .

 

.. warning::

   

  This operation is required only for organizations that were created explicitly with only the consolidated billing features enabled, or that were migrated from a Consolidated Billing account family to Organizations. Calling this operation sends a handshake to every invited account in the organization. The feature set change can be finalized and the additional features enabled only after all administrators in the invited accounts approve the change by accepting the handshake.

   

 

After all invited member accounts accept the handshake, you finalize the feature set change by accepting the handshake that contains ``"Action": "ENABLE_ALL_FEATURES"`` . This completes the change.

 

After you enable all features in your organization, the master account in the organization can apply policies on all member accounts. These policies can restrict what users and even administrators in those accounts can do. The master account can apply policies that prevent accounts from leaving the organization. Ensure that your account administrators are aware of this.

 

This operation can be called only from the organization's master account. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/EnableAllFeatures>`_


========
Synopsis
========

::

    enable-all-features
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable all features in an organization**

This example shows the administrator asking all the invited accounts in the organization to approve enabled all features in the organization. AWS Organizations sends an email to the address that is registered with every invited member account asking the owner to approve the change to all features by accepting the handshake that is sent. After all invited member accounts accept the handshake, the organization administrator can finalize the change to all features, and those with appropriate permissions can create policies and apply them to roots, OUs, and accounts. 

Command::

  aws organizations enable-all-features
  
Output::

  {
    "Handshake": {
      "Action": "ENABLE_ALL_FEATURES",
      "Arn":"arn:aws:organizations::111111111111:handshake/o-exampleorgid/enable_all_features/h-examplehandshakeid111",
      "ExpirationTimestamp":1.483127868609E9,
      "Id":"h-examplehandshakeid111",
      "Parties": [
        {
          "id":"o-exampleorgid",
          "type":"ORGANIZATION"
        }
      ],
      "requestedTimestamp":1.481831868609E9,
      "resources": [
        {
          "type":"ORGANIZATION",
          "value":"o-exampleorgid"
        }
      ],
      "state":"REQUESTED"
    }
  }

======
Output
======

Handshake -> (structure)

  

  A structure that contains details about the handshake created to support this request to enable all features in the organization.

  

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
             

            

            

          

        

      

    

  

