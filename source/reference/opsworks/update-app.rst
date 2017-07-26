[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-app:


**********
update-app
**********



===========
Description
===========



Updates a specified app.

 

**Required Permissions** : To use this action, an IAM user must have a Deploy or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-app
  --app-id <value>
  [--name <value>]
  [--description <value>]
  [--data-sources <value>]
  [--type <value>]
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

``--app-id`` (string)


  The app ID.

  

``--name`` (string)


  The app name.

  

``--description`` (string)


  A description of the app.

  

``--data-sources`` (list)


  The app's data sources.

  



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


  The app type.

  

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


  The app's virtual host settings, with multiple domains separated by commas. For example: ``'www.example.com, example.com'`` 

  



Syntax::

  "string" "string" ...



``--enable-ssl`` | ``--no-enable-ssl`` (boolean)


  Whether SSL is enabled for the app.

  

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


  An array of ``EnvironmentVariable`` objects that specify environment variables to be associated with the app. After you deploy the app, these variables are defined on the associated app server instances.For more information, see `Environment Variables`_ .

   

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

**To update an app**

The following example updates a specified app to change its name. ::

  aws opsworks --region us-east-1 update-app --app-id 26a61ead-d201-47e3-b55c-2a7c666942f8 --name NewAppName

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Editing Apps`_ in the *AWS OpsWorks User Guide*.

.. _`Editing Apps`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-editing.html



======
Output
======

None

.. _Environment Variables: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html#workingapps-creating-environment
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
