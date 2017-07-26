[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces describe-workspaces:


*******************
describe-workspaces
*******************



===========
Description
===========



Obtains information about the specified WorkSpaces. 

 

Only one of the filter parameters, such as ``bundle-id`` , ``directory-id`` , or ``WorkspaceIds`` , can be specified at a time.

 

This operation supports pagination with the use of the ``NextToken`` request and response parameters. If more results are available, the ``NextToken`` response member contains a token that you pass in the next call to this operation to retrieve the next set of items.



========
Synopsis
========

::

    describe-workspaces
  [--workspace-ids <value>]
  [--directory-id <value>]
  [--user-name <value>]
  [--bundle-id <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--workspace-ids`` (list)


  An array of strings that contain the identifiers of the WorkSpaces for which to retrieve information. This parameter cannot be combined with any other filter parameter.

   

  Because the  create-workspaces operation is asynchronous, the identifier returned by  create-workspaces is not immediately available. If you immediately call  describe-workspaces with this identifier, no information will be returned.

  



Syntax::

  "string" "string" ...



``--directory-id`` (string)


  Specifies the directory identifier to which to limit the WorkSpaces. Optionally, you can specify a specific directory user with the ``user-name`` parameter. This parameter cannot be combined with any other filter parameter.

  

``--user-name`` (string)


  Used with the ``directory-id`` parameter to specify the directory user for which to obtain the WorkSpace.

  

``--bundle-id`` (string)


  The identifier of a bundle to obtain the WorkSpaces for. All WorkSpaces that are created from this bundle will be retrieved. This parameter cannot be combined with any other filter parameter.

  

``--limit`` (integer)


  The maximum number of items to return.

  

``--next-token`` (string)


  The ``NextToken`` value from a previous call to this operation. Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your WorkSpaces**

This example describes all of your WorkSpaces in the region.

Command::

  aws workspaces describe-workspaces

Output::

  {
    "Workspaces" : [
      {
        "UserName" : "johndoe",
        "DirectoryId" : "d-906732325d",
        "State" : "AVAILABLE",
        "WorkspaceId" : "ws-3lvdznndy",
        "SubnetId" : "subnet-435c036b",
        "IpAddress" : "50.0.1.10",
        "BundleId" : "wsb-86y2d88pq"
      },
      {
        "UserName": "jimsmith",
        "DirectoryId": "d-906732325d",
        "State": "PENDING",
        "WorkspaceId": "ws-0d4y2sbl5",
        "BundleId": "wsb-b0s22j3d7"
      },
      {
        "UserName" : "marym",
        "DirectoryId" : "d-906732325d",
        "State" : "AVAILABLE",
        "WorkspaceId" : "ws-b3vg4shrh",
        "SubnetId" : "subnet-775a6531",
        "IpAddress" : "50.0.0.5",
        "BundleId" : "wsb-3t36q0xfc"
      }
    ]
  }


======
Output
======

Workspaces -> (list)

  

  An array of structures that contain the information about the WorkSpaces.

   

  Because the  create-workspaces operation is asynchronous, some of this information may be incomplete for a newly-created WorkSpace.

  

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

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``NextToken`` parameter in a subsequent call to this operation to retrieve the next set of items. This token is valid for one day and must be used within that timeframe.

  

  

