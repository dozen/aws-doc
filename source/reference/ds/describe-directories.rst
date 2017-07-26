[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-directories:


********************
describe-directories
********************



===========
Description
===========



Obtains information about the directories that belong to this account.

 

You can retrieve information about specific directories by passing the directory identifiers in the *directory-ids* parameter. Otherwise, all directories that belong to the current account are returned.

 

This operation supports pagination with the use of the *next-token* request and response parameters. If more results are available, the *DescribeDirectoriesResult.NextToken* member contains a token that you pass in the next call to  describe-directories to retrieve the next set of items.

 

You can also specify a maximum number of return results with the *limit* parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeDirectories>`_


========
Synopsis
========

::

    describe-directories
  [--directory-ids <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-ids`` (list)


  A list of identifiers of the directories for which to obtain the information. If this member is null, all directories that belong to the current account are returned.

   

  An empty list results in an ``InvalidParameterException`` being thrown.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The *DescribeDirectoriesResult.NextToken* value from a previous call to  describe-directories . Pass null if this is the first call.

  

``--limit`` (integer)


  The maximum number of items to return. If this value is zero, the maximum number of items is specified by the limitations of the operation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryDescriptions -> (list)

  

  The list of  DirectoryDescription objects that were retrieved.

   

  It is possible that this list contains less than the number of items specified in the *limit* member of the request. This occurs if there are less than the requested number of items left to retrieve, or if the limitations of the operation have been exceeded.

  

  (structure)

    

    Contains information about an AWS Directory Service directory.

    

    DirectoryId -> (string)

      

      The directory identifier.

      

      

    Name -> (string)

      

      The fully-qualified name of the directory.

      

      

    ShortName -> (string)

      

      The short name of the directory.

      

      

    Size -> (string)

      

      The directory size.

      

      

    Alias -> (string)

      

      The alias for the directory. If no alias has been created for the directory, the alias is the directory identifier, such as ``d-XXXXXXXXXX`` .

      

      

    AccessUrl -> (string)

      

      The access URL for the directory, such as ``http://alias.awsapps.com`` . If no alias has been created for the directory, ``alias`` is the directory identifier, such as ``d-XXXXXXXXXX`` .

      

      

    Description -> (string)

      

      The textual description for the directory.

      

      

    DnsIpAddrs -> (list)

      

      The IP addresses of the DNS servers for the directory. For a Simple AD or Microsoft AD directory, these are the IP addresses of the Simple AD or Microsoft AD directory servers. For an AD Connector directory, these are the IP addresses of the DNS servers or domain controllers in the on-premises directory to which the AD Connector is connected.

      

      (string)

        

        

      

    Stage -> (string)

      

      The current stage of the directory.

      

      

    LaunchTime -> (timestamp)

      

      Specifies when the directory was created.

      

      

    StageLastUpdatedDateTime -> (timestamp)

      

      The date and time that the stage was last updated.

      

      

    Type -> (string)

      

      The directory size.

      

      

    VpcSettings -> (structure)

      

      A  DirectoryVpcSettingsDescription object that contains additional information about a directory. This member is only present if the directory is a Simple AD or Managed AD directory.

      

      VpcId -> (string)

        

        The identifier of the VPC that the directory is in.

        

        

      SubnetIds -> (list)

        

        The identifiers of the subnets for the directory servers.

        

        (string)

          

          

        

      SecurityGroupId -> (string)

        

        The security group identifier for the directory. If the directory was created before 8/1/2014, this is the identifier of the directory members security group that was created when the directory was created. If the directory was created after this date, this value is null.

        

        

      AvailabilityZones -> (list)

        

        The list of Availability Zones that the directory is in.

        

        (string)

          

          

        

      

    ConnectSettings -> (structure)

      

      A  DirectoryConnectSettingsDescription object that contains additional information about an AD Connector directory. This member is only present if the directory is an AD Connector directory.

      

      VpcId -> (string)

        

        The identifier of the VPC that the AD Connector is in.

        

        

      SubnetIds -> (list)

        

        A list of subnet identifiers in the VPC that the AD connector is in.

        

        (string)

          

          

        

      CustomerUserName -> (string)

        

        The username of the service account in the on-premises directory.

        

        

      SecurityGroupId -> (string)

        

        The security group identifier for the AD Connector directory.

        

        

      AvailabilityZones -> (list)

        

        A list of the Availability Zones that the directory is in.

        

        (string)

          

          

        

      ConnectIps -> (list)

        

        The IP addresses of the AD Connector servers.

        

        (string)

          

          

        

      

    RadiusSettings -> (structure)

      

      A  RadiusSettings object that contains information about the RADIUS server configured for this directory.

      

      RadiusServers -> (list)

        

        An array of strings that contains the IP addresses of the RADIUS server endpoints, or the IP addresses of your RADIUS server load balancer.

        

        (string)

          

          

        

      RadiusPort -> (integer)

        

        The port that your RADIUS server is using for communications. Your on-premises network must allow inbound traffic over this port from the AWS Directory Service servers.

        

        

      RadiusTimeout -> (integer)

        

        The amount of time, in seconds, to wait for the RADIUS server to respond.

        

        

      RadiusRetries -> (integer)

        

        The maximum number of times that communication with the RADIUS server is attempted.

        

        

      SharedSecret -> (string)

        

        Not currently used.

        

        

      AuthenticationProtocol -> (string)

        

        The protocol specified for your RADIUS endpoints.

        

        

      DisplayLabel -> (string)

        

        Not currently used.

        

        

      UseSameUsername -> (boolean)

        

        Not currently used.

        

        

      

    RadiusStatus -> (string)

      

      The status of the RADIUS MFA server connection.

      

      

    StageReason -> (string)

      

      Additional information about the directory stage.

      

      

    SsoEnabled -> (boolean)

      

      Indicates if single-sign on is enabled for the directory. For more information, see  enable-sso and  disable-sso .

      

      

    DesiredNumberOfDomainControllers -> (integer)

      

      The desired number of domain controllers in the directory if the directory is Microsoft AD.

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the *next-token* parameter in a subsequent call to  describe-directories to retrieve the next set of items.

  

  

