[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-stacks:


***************
describe-stacks
***************



===========
Description
===========



Requests a description of one or more stacks.

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-stacks
  [--stack-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-ids`` (list)


  An array of stack IDs that specify the stacks to be described. If you omit this parameter, ``describe-stacks`` returns a description of every stack.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe stacks**

The following ``describe-stacks`` command describes an account's stacks. ::

  aws opsworks --region us-east-1 describe-stacks

**Note**: AWS OpsWorks CLI commands should set the region to us-east-1 regardless of the stack's location.

*Output*::

  {
    "Stacks": [
      {
        "ServiceRoleArn": "arn:aws:iam::444455556666:role/aws-opsworks-service-role",
        "StackId": "aeb7523e-7c8b-49d4-b866-03aae9d4fbcb",
        "DefaultRootDeviceType": "instance-store",
        "Name": "TomStack-sd",
        "ConfigurationManager": {
          "Version": "11.4",
          "Name": "Chef"
        },
        "UseCustomCookbooks": true,
        "CustomJson": "{\n  \"tomcat\": {\n    \"base_version\": 7,\n    \"java_opts\": \"-Djava.awt.headless=true -Xmx256m\"\n  },\n  \"datasources\": {\n    \"ROOT\": \"jdbc/mydb\"\n  }\n}",
        "Region": "us-east-1",
        "DefaultInstanceProfileArn": "arn:aws:iam::444455556666:instance-profile/aws-opsworks-ec2-role",
        "CustomCookbooksSource": {
          "Url": "git://github.com/example-repo/tomcustom.git",
          "Type": "git"
        },
        "DefaultAvailabilityZone": "us-east-1a",
        "HostnameTheme": "Layer_Dependent",
        "Attributes": {
          "Color": "rgb(45, 114, 184)"
        },
        "DefaultOs": "Amazon Linux",
        "CreatedAt": "2013-08-01T22:53:42+00:00"
      },
      {
        "ServiceRoleArn": "arn:aws:iam::444455556666:role/aws-opsworks-service-role",
        "StackId": "40738975-da59-4c5b-9789-3e422f2cf099",
        "DefaultRootDeviceType": "instance-store",
        "Name": "MyStack",
        "ConfigurationManager": {
          "Version": "11.4",
          "Name": "Chef"
        },
        "UseCustomCookbooks": false,
        "Region": "us-east-1",
        "DefaultInstanceProfileArn": "arn:aws:iam::444455556666:instance-profile/aws-opsworks-ec2-role",
        "CustomCookbooksSource": {},
        "DefaultAvailabilityZone": "us-east-1a",
        "HostnameTheme": "Layer_Dependent",
        "Attributes": {
          "Color": "rgb(45, 114, 184)"
        },
        "DefaultOs": "Amazon Linux",
        "CreatedAt": "2013-10-25T19:24:30+00:00"
      }
    ]
  }

**More Information**

For more information, see `Stacks`_ in the *AWS OpsWorks User Guide*.

.. _`Stacks`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks.html



======
Output
======

Stacks -> (list)

  

  An array of ``Stack`` objects that describe the stacks.

  

  (structure)

    

    Describes a stack.

    

    StackId -> (string)

      

      The stack ID.

      

      

    Name -> (string)

      

      The stack name.

      

      

    Arn -> (string)

      

      The stack's ARN.

      

      

    Region -> (string)

      

      The stack AWS region, such as "us-east-1". For more information about AWS regions, see `Regions and Endpoints`_ .

      

      

    VpcId -> (string)

      

      The VPC ID; applicable only if the stack is running in a VPC.

      

      

    Attributes -> (map)

      

      The stack's attributes.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    ServiceRoleArn -> (string)

      

      The stack AWS Identity and Access Management (IAM) role.

      

      

    DefaultInstanceProfileArn -> (string)

      

      The ARN of an IAM profile that is the default profile for all of the stack's EC2 instances. For more information about IAM ARNs, see `Using Identifiers`_ .

      

      

    DefaultOs -> (string)

      

      The stack's default operating system. 

      

      

    HostnameTheme -> (string)

      

      The stack host name theme, with spaces replaced by underscores.

      

      

    DefaultAvailabilityZone -> (string)

      

      The stack's default Availability Zone. For more information, see `Regions and Endpoints`_ .

      

      

    DefaultSubnetId -> (string)

      

      The default subnet ID; applicable only if the stack is running in a VPC.

      

      

    CustomJson -> (string)

      

      A JSON object that contains user-defined attributes to be added to the stack configuration and deployment attributes. You can use custom JSON to override the corresponding default stack configuration attribute values or to pass data to recipes. The string should be in the following format and must escape characters such as '"':

       

       ``"{\"key1\": \"value1\", \"key2\": \"value2\",...}"``  

       

      For more information on custom JSON, see `Use Custom JSON to Modify the Stack Configuration Attributes`_ .

      

      

    ConfigurationManager -> (structure)

      

      The configuration manager.

      

      Name -> (string)

        

        The name. This parameter must be set to "Chef".

        

        

      Version -> (string)

        

        The Chef version. This parameter must be set to 12, 11.10, or 11.4 for Linux stacks, and to 12.2 for Windows stacks. The default value for Linux stacks is 11.4.

        

        

      

    ChefConfiguration -> (structure)

      

      A ``ChefConfiguration`` object that specifies whether to enable Berkshelf and the Berkshelf version. For more information, see `Create a New Stack`_ .

      

      ManageBerkshelf -> (boolean)

        

        Whether to enable Berkshelf.

        

        

      BerkshelfVersion -> (string)

        

        The Berkshelf version.

        

        

      

    UseCustomCookbooks -> (boolean)

      

      Whether the stack uses custom cookbooks.

      

      

    UseOpsworksSecurityGroups -> (boolean)

      

      Whether the stack automatically associates the AWS OpsWorks built-in security groups with the stack's layers.

      

      

    CustomCookbooksSource -> (structure)

      

      Contains the information required to retrieve an app or cookbook from a repository. For more information, see `Creating Apps`_ or `Custom Recipes and Cookbooks`_ .

      

      Type -> (string)

        

        The repository type.

        

        

      Url -> (string)

        

        The source URL. 

        

        

      Username -> (string)

        

        This parameter depends on the repository type. 

         

         
        * For Amazon S3 bundles, set ``Username`` to the appropriate IAM access key ID.
         
        * For HTTP bundles, Git repositories, and Subversion repositories, set ``Username`` to the user name.
         

        

        

      Password -> (string)

        

        When included in a request, the parameter depends on the repository type. 

         

         
        * For Amazon S3 bundles, set ``Password`` to the appropriate IAM secret access key.
         
        * For HTTP bundles and Subversion repositories, set ``Password`` to the password.
         

         

        For more information on how to safely handle IAM credentials, see `<http://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html>`_ .

         

        In responses, AWS OpsWorks returns ``*****FILTERED*****`` instead of the actual value.

        

        

      SshKey -> (string)

        

        In requests, the repository's SSH key.

         

        In responses, AWS OpsWorks returns ``*****FILTERED*****`` instead of the actual value.

        

        

      Revision -> (string)

        

        The application's version. AWS OpsWorks enables you to easily deploy new versions of an application. One of the simplest approaches is to have branches or revisions in your repository that represent different versions that can potentially be deployed.

        

        

      

    DefaultSshKeyName -> (string)

      

      A default Amazon EC2 key pair for the stack's instances. You can override this value when you create or update an instance.

      

      

    CreatedAt -> (string)

      

      The date when the stack was created.

      

      

    DefaultRootDeviceType -> (string)

      

      The default root device type. This value is used by default for all instances in the stack, but you can override it when you create an instance. For more information, see `Storage for the Root Device`_ .

      

      

    AgentVersion -> (string)

      

      The agent version. This parameter is set to ``LATEST`` for auto-update. or a version number for a fixed agent version.

      

      

    

  



.. _Creating Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html
.. _Custom Recipes and Cookbooks: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook.html
.. _Use Custom JSON to Modify the Stack Configuration Attributes: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-json.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
.. _Create a New Stack: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-creating.html
.. _Storage for the Root Device: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html#storage-for-the-root-device
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
