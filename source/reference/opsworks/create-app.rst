[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-app:


**********
create-app
**********



===========
Description
===========



Creates an app for a specified stack. For more information, see `Creating Apps`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    create-app
  --stack-id <value>
  [--shortname <value>]
  --name <value>
  [--description <value>]
  [--data-sources <value>]
  --type <value>
  [--app-source <value>]
  [--domains <value>]
  [--enable-ssl | --no-enable-ssl]
  [--ssl-configuration <value>]
  [--attributes <value>]
  [--environment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--shortname`` (string)


  The app's short name.

  

``--name`` (string)


  The app name.

  

``--description`` (string)


  A description of the app.

  

``--data-sources`` (list)


  The app's data source.

  



Shorthand Syntax::

    Type=string,Arn=string,DatabaseName=string ...




JSON Syntax::

  [
    {
      "Type": "string",
      "Arn": "string",
      "DatabaseName": "string"
    }
    ...
  ]



``--type`` (string)


  The app type. Each supported type is associated with a particular layer. For example, PHP applications are associated with a PHP layer. AWS OpsWorks deploys an application to those instances that are members of the corresponding layer. If your app isn't one of the standard types, or you prefer to implement your own Deploy recipes, specify ``other`` .

  

  Possible values:

  
  *   ``aws-flow-ruby``

  
  *   ``java``

  
  *   ``rails``

  
  *   ``php``

  
  *   ``nodejs``

  
  *   ``static``

  
  *   ``other``

  

  

``--app-source`` (structure)


  A ``app-source`` object that specifies the app repository.

  



Shorthand Syntax::

    Type=string,Url=string,Username=string,Password=string,SshKey=string,Revision=string




JSON Syntax::

  {
    "Type": "git"|"svn"|"archive"|"s3",
    "Url": "string",
    "Username": "string",
    "Password": "string",
    "SshKey": "string",
    "Revision": "string"
  }



``--domains`` (list)


  The app virtual host settings, with multiple domains separated by commas. For example: ``'www.example.com, example.com'`` 

  



Syntax::

  "string" "string" ...



``--enable-ssl`` | ``--no-enable-ssl`` (boolean)


  Whether to enable SSL for the app.

  

``--ssl-configuration`` (structure)


  An ``ssl-configuration`` object with the SSL configuration.

  



Shorthand Syntax::

    Certificate=string,PrivateKey=string,Chain=string




JSON Syntax::

  {
    "Certificate": "string",
    "PrivateKey": "string",
    "Chain": "string"
  }



``--attributes`` (map)


  One or more user-defined key/value pairs to be added to the stack attributes.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
    DocumentRoot
    RailsEnv
    AutoBundleOnDeploy
    AwsFlowRubySettings




JSON Syntax::

  {"DocumentRoot"|"RailsEnv"|"AutoBundleOnDeploy"|"AwsFlowRubySettings": "string"
    ...}



``--environment`` (list)


  An array of ``EnvironmentVariable`` objects that specify environment variables to be associated with the app. After you deploy the app, these variables are defined on the associated app server instance. For more information, see `Environment Variables`_ .

   

  There is no specific limit on the number of environment variables. However, the size of the associated data structure - which includes the variables' names, values, and protected flag values - cannot exceed 10 KB (10240 Bytes). This limit should accommodate most if not all use cases. Exceeding it will cause an exception with the message, "Environment: is too large (maximum is 10KB)." 

   

  .. note::

    This parameter is supported only by Chef 11.10 stacks. If you have specified one or more environment variables, you cannot modify the stack's Chef version.

  



Shorthand Syntax::

    Key=string,Value=string,Secure=boolean ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string",
      "Secure": true|false
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an app**

The following example creates a PHP app named SimplePHPApp from code stored in a GitHub repository.
The command uses the shorthand form of the application source definition. ::

  aws opsworks --region us-east-1 create-app --stack-id f6673d70-32e6-4425-8999-265dd002fec7 --name SimplePHPApp --type php --app-source Type=git,Url=git://github.com/amazonwebservices/opsworks-demo-php-simple-app.git,Revision=version1

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "AppId": "6cf5163c-a951-444f-a8f7-3716be75f2a2"
  }

**To create an app with an attached database**

The following example creates a JSP app from code stored in .zip archive in a public S3 bucket.
It attaches an RDS DB instance to serve as the app's data store. The application and database sources are defined in separate
JSON files that are in the directory from which you run the command. ::

  aws opsworks --region us-east-1 create-app --stack-id 8c428b08-a1a1-46ce-a5f8-feddc43771b8 --name SimpleJSP --type java --app-source file://appsource.json --data-sources file://datasource.json 

The application source information is in ``appsource.json`` and contains the following. ::

  {
    "Type": "archive",
    "Url": "https://s3.amazonaws.com/jsp_example/simplejsp.zip"
  }

The database source information is in ``datasource.json`` and contains the following. ::

  [
    {
      "Type": "RdsDbInstance",
      "Arn": "arn:aws:rds:us-west-2:123456789012:db:clitestdb",
      "DatabaseName": "mydb"
    }
  ]
  
**Note**: For an RDS DB instance, you must first use ``register-rds-db-instance`` to register the instance with the stack.
For MySQL App Server instances, set ``Type`` to ``OpsworksMysqlInstance``. These instances are
created by AWS OpsWorks,
so they do not have to be registered.

*Output*::

  {
    "AppId": "26a61ead-d201-47e3-b55c-2a7c666942f8"
  }

For more information, see `Adding Apps`_ in the *AWS OpsWorks User Guide*.

.. _`Adding Apps`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html



======
Output
======

AppId -> (string)

  

  The app ID.

  

  



.. _Environment Variables: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html#workingapps-creating-environment
.. _Creating Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
