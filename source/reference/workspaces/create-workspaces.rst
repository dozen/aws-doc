[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces create-workspaces:


*****************
create-workspaces
*****************



===========
Description
===========



Creates one or more WorkSpaces.

 

.. note::

   

  This operation is asynchronous and returns before the WorkSpaces are created.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/CreateWorkspaces>`_


========
Synopsis
========

::

    create-workspaces
  --workspaces <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--workspaces`` (list)


  An array of structures that specify the WorkSpaces to create.

  



Shorthand Syntax::

    DirectoryId=string,UserName=string,BundleId=string,VolumeEncryptionKey=string,UserVolumeEncryptionEnabled=boolean,RootVolumeEncryptionEnabled=boolean,WorkspaceProperties={RunningMode=string,RunningModeAutoStopTimeoutInMinutes=integer},Tags=[{Key=string,Value=string},{Key=string,Value=string}] ...




JSON Syntax::

  [
    {
      "DirectoryId": "string",
      "UserName": "string",
      "BundleId": "string",
      "VolumeEncryptionKey": "string",
      "UserVolumeEncryptionEnabled": true|false,
      "RootVolumeEncryptionEnabled": true|false,
      "WorkspaceProperties": {
        "RunningMode": "AUTO_STOP"|"ALWAYS_ON",
        "RunningModeAutoStopTimeoutInMinutes": integer
      },
      "Tags": [
        {
          "Key": "string",
          "Value": "string"
        }
        ...
      ]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a WorkSpace**

This example creates a WorkSpace for user ``jimsmith`` in the specified directory, from the specified bundle.

Command::

  aws workspaces create-workspaces --cli-input-json file://create-workspaces.json

Input::

  This is the contents of the create-workspaces.json file:

  {
    "Workspaces" : [
      {
        "DirectoryId" : "d-906732325d",
        "UserName" : "jimsmith",
        "BundleId" : "wsb-b0s22j3d7"
      }
    ]
  }

Output::

  {
    "PendingRequests" : [
      {
        "UserName" : "jimsmith",
        "DirectoryId" : "d-906732325d",
        "State" : "PENDING",
        "WorkspaceId" : "ws-0d4y2sbl5",
        "BundleId" : "wsb-b0s22j3d7"
      }
    ],
    "FailedRequests" : []
  }


======
Output
======

FailedRequests -> (list)

  

  An array of structures that represent the WorkSpaces that could not be created.

  

  (structure)

    

    Contains information about a WorkSpace that could not be created.

    

    WorkspaceRequest -> (structure)

      

      A  FailedCreateWorkspaceRequest$WorkspaceRequest object that contains the information about the WorkSpace that could not be created.

      

      DirectoryId -> (string)

        

        The identifier of the AWS Directory Service directory to create the WorkSpace in. You can use the  describe-workspace-directories operation to obtain a list of the directories that are available.

        

        

      UserName -> (string)

        

        The username that the WorkSpace is assigned to. This username must exist in the AWS Directory Service directory specified by the ``DirectoryId`` member.

        

        

      BundleId -> (string)

        

        The identifier of the bundle to create the WorkSpace from. You can use the  describe-workspace-bundles operation to obtain a list of the bundles that are available.

        

        

      VolumeEncryptionKey -> (string)

        

        The KMS key used to encrypt data stored on your WorkSpace.

        

        

      UserVolumeEncryptionEnabled -> (boolean)

        

        Specifies whether the data stored on the user volume, or D: drive, is encrypted.

        

        

      RootVolumeEncryptionEnabled -> (boolean)

        

        Specifies whether the data stored on the root volume, or C: drive, is encrypted.

        

        

      WorkspaceProperties -> (structure)

        

        Describes the properties of a WorkSpace.

        

        RunningMode -> (string)

          

          The running mode of the WorkSpace. AlwaysOn WorkSpaces are billed monthly. AutoStop WorkSpaces are billed by the hour and stopped when no longer being used in order to save on costs.

          

          

        RunningModeAutoStopTimeoutInMinutes -> (integer)

          

          The time after a user logs off when WorkSpaces are automatically stopped. Configured in 60 minute intervals.

          

          

        

      Tags -> (list)

        

        The tags of the WorkSpace request.

        

        (structure)

          

          Describes the tag of the WorkSpace.

          

          Key -> (string)

            

            The key of the tag.

            

            

          Value -> (string)

            

            The value of the tag.

            

            

          

        

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

PendingRequests -> (list)

  

  An array of structures that represent the WorkSpaces that were created.

   

  Because this operation is asynchronous, the identifier in ``WorkspaceId`` is not immediately available. If you immediately call  describe-workspaces with this identifier, no information will be returned.

  

  (structure)

    

    Contains information about a WorkSpace.

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    DirectoryId -> (string)

      

      The identifier of the AWS Directory Service directory that the WorkSpace belongs to.

      

      

    UserName -> (string)

      

      The user that the WorkSpace is assigned to.

      

      

    IpAddress -> (string)

      

      The IP address of the WorkSpace.

      

      

    State -> (string)

      

      The operational state of the WorkSpace.

      

      

    BundleId -> (string)

      

      The identifier of the bundle that the WorkSpace was created from.

      

      

    SubnetId -> (string)

      

      The identifier of the subnet that the WorkSpace is in.

      

      

    ErrorMessage -> (string)

      

      If the WorkSpace could not be created, this contains a textual error message that describes the failure.

      

      

    ErrorCode -> (string)

      

      If the WorkSpace could not be created, this contains the error code.

      

      

    ComputerName -> (string)

      

      The name of the WorkSpace as seen by the operating system.

      

      

    VolumeEncryptionKey -> (string)

      

      The KMS key used to encrypt data stored on your WorkSpace.

      

      

    UserVolumeEncryptionEnabled -> (boolean)

      

      Specifies whether the data stored on the user volume, or D: drive, is encrypted.

      

      

    RootVolumeEncryptionEnabled -> (boolean)

      

      Specifies whether the data stored on the root volume, or C: drive, is encrypted.

      

      

    WorkspaceProperties -> (structure)

      

      Describes the properties of a WorkSpace.

      

      RunningMode -> (string)

        

        The running mode of the WorkSpace. AlwaysOn WorkSpaces are billed monthly. AutoStop WorkSpaces are billed by the hour and stopped when no longer being used in order to save on costs.

        

        

      RunningModeAutoStopTimeoutInMinutes -> (integer)

        

        The time after a user logs off when WorkSpaces are automatically stopped. Configured in 60 minute intervals.

        

        

      

    

  

