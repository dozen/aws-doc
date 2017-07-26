[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-apps:


*************
describe-apps
*************



===========
Description
===========



Requests a description of a specified set of apps.

 

.. note::

   

  You must specify at least one of the parameters.

   

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-apps
  [--stack-id <value>]
  [--app-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The app stack ID. If you use this parameter, ``describe-apps`` returns a description of the apps in the specified stack.

  

``--app-ids`` (list)


  An array of app IDs for the apps to be described. If you use this parameter, ``describe-apps`` returns a description of the specified apps. Otherwise, it returns a description of every app.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe apps**

The following ``describe-apps`` command describes the apps in a specified stack.  ::

  aws opsworks --region us-east-1 describe-apps --stack-id 38ee91e2-abdc-4208-a107-0b7168b3cc7a

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: This particular stack has one app.

::

  {
    "Apps": [
      {
        "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
        "AppSource": {
          "Url": "https://s3-us-west-2.amazonaws.com/opsworks-tomcat/simplejsp.zip",
          "Type": "archive"
        },
        "Name": "SimpleJSP",
        "EnableSsl": false,
        "SslConfiguration": {},
        "AppId": "da1decc1-0dff-43ea-ad7c-bb667cd87c8b",
        "Attributes": {
          "RailsEnv": null,
          "AutoBundleOnDeploy": "true",
          "DocumentRoot": "ROOT"
        },
        "Shortname": "simplejsp",
        "Type": "other",
        "CreatedAt": "2013-08-01T21:46:54+00:00"
      }
    ]
  }

**More Information**

For more information, see Apps_ in the *AWS OpsWorks User Guide*.

.. _Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps.html



======
Output
======

Apps -> (list)

  

  An array of ``App`` objects that describe the specified apps. 

  

  (structure)

    

    A description of the app.

    

    AppId -> (string)

      

      The app ID.

      

      

    StackId -> (string)

      

      The app stack ID.

      

      

    Shortname -> (string)

      

      The app's short name.

      

      

    Name -> (string)

      

      The app name.

      

      

    Description -> (string)

      

      A description of the app.

      

      

    DataSources -> (list)

      

      The app's data sources.

      

      (structure)

        

        Describes an app's data source.

        

        Type -> (string)

          

          The data source's type, ``AutoSelectOpsworksMysqlInstance`` , ``OpsworksMysqlInstance`` , or ``RdsDbInstance`` .

          

          

        Arn -> (string)

          

          The data source's ARN.

          

          

        DatabaseName -> (string)

          

          The database name.

          

          

        

      

    Type -> (string)

      

      The app type.

      

      

    AppSource -> (structure)

      

      A ``Source`` object that describes the app repository.

      

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

        

        

      

    Domains -> (list)

      

      The app vhost settings with multiple domains separated by commas. For example: ``'www.example.com, example.com'`` 

      

      (string)

        

        

      

    EnableSsl -> (boolean)

      

      Whether to enable SSL for the app.

      

      

    SslConfiguration -> (structure)

      

      An ``SslConfiguration`` object with the SSL configuration.

      

      Certificate -> (string)

        

        The contents of the certificate's domain.crt file.

        

        

      PrivateKey -> (string)

        

        The private key; the contents of the certificate's domain.kex file.

        

        

      Chain -> (string)

        

        Optional. Can be used to specify an intermediate certificate authority key or client authentication.

        

        

      

    Attributes -> (map)

      

      The stack attributes.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    CreatedAt -> (string)

      

      When the app was created.

      

      

    Environment -> (list)

      

      An array of ``EnvironmentVariable`` objects that specify environment variables to be associated with the app. After you deploy the app, these variables are defined on the associated app server instances. For more information, see `Environment Variables`_ . 

       

      .. note::

        There is no specific limit on the number of environment variables. However, the size of the associated data structure - which includes the variables' names, values, and protected flag values - cannot exceed 10 KB (10240 Bytes). This limit should accommodate most if not all use cases, but if you do exceed it, you will cause an exception (API) with an "Environment: is too large (maximum is 10KB)" message. 

      

      (structure)

        

        Represents an app's environment variable.

        

        Key -> (string)

          

          (Required) The environment variable's name, which can consist of up to 64 characters and must be specified. The name can contain upper- and lowercase letters, numbers, and underscores (_), but it must start with a letter or underscore.

          

          

        Value -> (string)

          

          (Optional) The environment variable's value, which can be left empty. If you specify a value, it can contain up to 256 characters, which must all be printable.

          

          

        Secure -> (boolean)

          

          (Optional) Whether the variable's value will be returned by the  describe-apps action. To conceal an environment variable's value, set ``Secure`` to ``true`` . ``describe-apps`` then returns ``*****FILTERED*****`` instead of the actual value. The default value for ``Secure`` is ``false`` . 

          

          

        

      

    

  



.. _Environment Variables: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html#workingapps-creating-environment
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
