[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces describe-workspace-directories:


******************************
describe-workspace-directories
******************************



===========
Description
===========



Retrieves information about the AWS Directory Service directories in the region that are registered with Amazon WorkSpaces and are available to your account.

 

This operation supports pagination with the use of the ``NextToken`` request and response parameters. If more results are available, the ``NextToken`` response member contains a token that you pass in the next call to this operation to retrieve the next set of items.



========
Synopsis
========

::

    describe-workspace-directories
  [--directory-ids <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-ids`` (list)


  An array of strings that contains the directory identifiers to retrieve information for. If this member is null, all directories are retrieved.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The ``NextToken`` value from a previous call to this operation. Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your WorkSpace directories**

This example describes all of your WorkSpace directories.

Command::

  aws workspaces describe-workspace-directories

Output::

  {
    "Directories" : [
      {
        "CustomerUserName" : "Administrator",
        "DirectoryId" : "d-906735683d",
        "DirectoryName" : "example.awsapps.com",
        "SubnetIds" : [
          "subnet-af0e2a87",
          "subnet-657e7a23"
        ],
        "WorkspaceCreationProperties" :
        {
          "EnableInternetAccess" : false,
          "EnableWorkDocs" : false,
          "UserEnabledAsLocalAdministrator" : true
        },
        "Alias" : "example",
        "State" : "REGISTERED",
        "DirectoryType" : "SIMPLE_AD",
        "RegistrationCode" : "SLiad+S393HD",
        "IamRoleId" : "arn:aws:iam::972506530580:role/workspaces_DefaultRole",
        "DnsIpAddresses" : [
          "10.0.2.190",
          "10.0.1.202"
        ],
        "WorkspaceSecurityGroupId" : "sg-6e40640b"
      },
      {
        "CustomerUserName" : "Administrator",
        "DirectoryId" : "d-906732325d",
        "DirectoryName" : "exampledomain.com",
        "SubnetIds" : [
          "subnet-775a6531",
          "subnet-435c036b"
        ],
        "WorkspaceCreationProperties" :
        {
          "EnableInternetAccess" : false,
          "EnableWorkDocs" : true,
          "UserEnabledAsLocalAdministrator" : true
        },
        "Alias" : "example-domain",
        "State" : "REGISTERED",
        "DirectoryType" : "AD_CONNECTOR",
        "RegistrationCode" : "SLiad+UBZGNH",
        "IamRoleId" : "arn:aws:iam::972506530580:role/workspaces_DefaultRole",
        "DnsIpAddresses" : [
          "50.0.2.223",
          "50.0.2.184"
        ]
      }
    ]
  }


======
Output
======

Directories -> (list)

  

  An array of structures that contain information about the directories.

  

  (structure)

    

    Contains information about an AWS Directory Service directory for use with Amazon WorkSpaces.

    

    DirectoryId -> (string)

      

      The directory identifier.

      

      

    Alias -> (string)

      

      The directory alias.

      

      

    DirectoryName -> (string)

      

      The name of the directory.

      

      

    RegistrationCode -> (string)

      

      The registration code for the directory. This is the code that users enter in their Amazon WorkSpaces client application to connect to the directory.

      

      

    SubnetIds -> (list)

      

      An array of strings that contains the identifiers of the subnets used with the directory.

      

      (string)

        

        

      

    DnsIpAddresses -> (list)

      

      An array of strings that contains the IP addresses of the DNS servers for the directory.

      

      (string)

        

        

      

    CustomerUserName -> (string)

      

      The user name for the service account.

      

      

    IamRoleId -> (string)

      

      The identifier of the IAM role. This is the role that allows Amazon WorkSpaces to make calls to other services, such as Amazon EC2, on your behalf.

      

      

    DirectoryType -> (string)

      

      The directory type.

      

      

    WorkspaceSecurityGroupId -> (string)

      

      The identifier of the security group that is assigned to new WorkSpaces.

      

      

    State -> (string)

      

      The state of the directory's registration with Amazon WorkSpaces

      

      

    WorkspaceCreationProperties -> (structure)

      

      A structure that specifies the default creation properties for all WorkSpaces in the directory.

      

      EnableWorkDocs -> (boolean)

        

        Specifies if the directory is enabled for Amazon WorkDocs.

        

        

      EnableInternetAccess -> (boolean)

        

        A public IP address will be attached to all WorkSpaces that are created or rebuilt.

        

        

      DefaultOu -> (string)

        

        The organizational unit (OU) in the directory that the WorkSpace machine accounts are placed in.

        

        

      CustomSecurityGroupId -> (string)

        

        The identifier of any custom security groups that are applied to the WorkSpaces when they are created.

        

        

      UserEnabledAsLocalAdministrator -> (boolean)

        

        The WorkSpace user is an administrator on the WorkSpace.

        

        

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``NextToken`` parameter in a subsequent call to this operation to retrieve the next set of items. This token is valid for one day and must be used within that timeframe.

  

  

