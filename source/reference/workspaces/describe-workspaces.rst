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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/DescribeWorkspaces>`_


``describe-workspaces`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Workspaces``


========
Synopsis
========

::

    describe-workspaces
  [--workspace-ids <value>]
  [--directory-id <value>]
  [--user-name <value>]
  [--bundle-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--workspace-ids`` (list)


  An array of strings that contain the identifiers of the WorkSpaces for which to retrieve information. This parameter cannot be combined with any other filter parameter.

   

  Because the  create-workspaces operation is asynchronous, the identifier it returns is not immediately available. If you immediately call  describe-workspaces with this identifier, no information is returned.

  



Syntax::

  "string" "string" ...



``--directory-id`` (string)


  Specifies the directory identifier to which to limit the WorkSpaces. Optionally, you can specify a specific directory user with the ``user-name`` parameter. This parameter cannot be combined with any other filter parameter.

  

``--user-name`` (string)


  Used with the ``directory-id`` parameter to specify the directory user for whom to obtain the WorkSpace.

  

``--bundle-id`` (string)


  The identifier of a bundle to obtain the WorkSpaces for. All WorkSpaces that are created from this bundle will be retrieved. This parameter cannot be combined with any other filter parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    WorkspaceProperties -> (structure)

      

      Describes the properties of a WorkSpace.

      

      RunningMode -> (string)

        

        The running mode of the WorkSpace. AlwaysOn WorkSpaces are billed monthly. AutoStop WorkSpaces are billed by the hour and stopped when no longer being used in order to save on costs.

        

        

      RunningModeAutoStopTimeoutInMinutes -> (integer)

        

        The time after a user logs off when WorkSpaces are automatically stopped. Configured in 60 minute intervals.

        

        

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``NextToken`` parameter in a subsequent call to this operation to retrieve the next set of items. This token is valid for one day and must be used within that time frame.

  

  

