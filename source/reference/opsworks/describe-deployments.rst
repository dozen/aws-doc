[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-deployments:


********************
describe-deployments
********************



===========
Description
===========



Requests a description of a specified set of deployments.

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeDeployments>`_


========
Synopsis
========

::

    describe-deployments
  [--stack-id <value>]
  [--app-id <value>]
  [--deployment-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID. If you include this parameter, ``describe-deployments`` returns a description of the commands associated with the specified stack.

  

``--app-id`` (string)


  The app ID. If you include this parameter, ``describe-deployments`` returns a description of the commands associated with the specified app.

  

``--deployment-ids`` (list)


  An array of deployment IDs to be described. If you include this parameter, ``describe-deployments`` returns a description of the specified deployments. Otherwise, it returns a description of every deployment.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe deployments**

The following ``describe-deployments`` commmand describes the deployments in a specified stack. ::

  aws opsworks --region us-east-1 describe-deployments --stack-id 38ee91e2-abdc-4208-a107-0b7168b3cc7a

*Output*::

  {
    "Deployments": [
        {
            "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
            "Status": "successful",
            "CompletedAt": "2013-07-25T18:57:49+00:00",
            "DeploymentId": "6ed0df4c-9ef7-4812-8dac-d54a05be1029",
            "Command": {
                "Args": {},
                "Name": "undeploy"
            },
            "CreatedAt": "2013-07-25T18:57:34+00:00",
            "Duration": 15,
            "InstanceIds": [
                "8c2673b9-3fe5-420d-9cfa-78d875ee7687",
                "9e588a25-35b2-4804-bd43-488f85ebe5b7"
            ]
        },
        {
            "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
            "Status": "successful",
            "CompletedAt": "2013-07-25T18:56:41+00:00",
            "IamUserArn": "arn:aws:iam::123456789012:user/someuser",
            "DeploymentId": "19d3121e-d949-4ff2-9f9d-94eac087862a",
            "Command": {
                "Args": {},
                "Name": "deploy"
            },
            "InstanceIds": [
                "8c2673b9-3fe5-420d-9cfa-78d875ee7687",
                "9e588a25-35b2-4804-bd43-488f85ebe5b7"
            ],
            "Duration": 72,
            "CreatedAt": "2013-07-25T18:55:29+00:00"
        }
    ]
  }

**More Information**

For more information, see `Deploying Apps`_ in the *AWS OpsWorks User Guide*.

.. _`Deploying Apps`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-deploying.html



======
Output
======

Deployments -> (list)

  

  An array of ``Deployment`` objects that describe the deployments.

  

  (structure)

    

    Describes a deployment of a stack or app.

    

    DeploymentId -> (string)

      

      The deployment ID.

      

      

    StackId -> (string)

      

      The stack ID.

      

      

    AppId -> (string)

      

      The app ID.

      

      

    CreatedAt -> (string)

      

      Date when the deployment was created.

      

      

    CompletedAt -> (string)

      

      Date when the deployment completed.

      

      

    Duration -> (integer)

      

      The deployment duration.

      

      

    IamUserArn -> (string)

      

      The user's IAM ARN.

      

      

    Comment -> (string)

      

      A user-defined comment.

      

      

    Command -> (structure)

      

      Used to specify a stack or deployment command.

      

      Name -> (string)

        

        Specifies the operation. You can specify only one command.

         

        For stacks, the following commands are available:

         

         
        * ``execute_recipes`` : Execute one or more recipes. To specify the recipes, set an ``Args`` parameter named ``recipes`` to the list of recipes to be executed. For example, to execute ``phpapp::appsetup`` , set ``Args`` to ``{"recipes":["phpapp::appsetup"]}`` . 
         
        * ``install_dependencies`` : Install the stack's dependencies. 
         
        * ``update_custom_cookbooks`` : Update the stack's custom cookbooks. 
         
        * ``update_dependencies`` : Update the stack's dependencies. 
         

         

        .. note::

           

          The update_dependencies and install_dependencies commands are supported only for Linux instances. You can run the commands successfully on Windows instances, but they do nothing.

           

         

        For apps, the following commands are available:

         

         
        * ``deploy`` : Deploy an app. Ruby on Rails apps have an optional ``Args`` parameter named ``migrate`` . Set ``Args`` to {"migrate":["true"]} to migrate the database. The default setting is {"migrate":["false"]}. 
         
        * ``rollback`` Roll the app back to the previous version. When you update an app, AWS OpsWorks Stacks stores the previous version, up to a maximum of five versions. You can use this command to roll an app back as many as four versions. 
         
        * ``start`` : Start the app's web or application server. 
         
        * ``stop`` : Stop the app's web or application server. 
         
        * ``restart`` : Restart the app's web or application server. 
         
        * ``undeploy`` : Undeploy the app. 
         

        

        

      Args -> (map)

        

        The arguments of those commands that take arguments. It should be set to a JSON object with the following format:

         

         ``{"arg_name1" : ["value1", "value2", ...], "arg_name2" : ["value1", "value2", ...], ...}``  

         

        The ``update_dependencies`` command takes two arguments:

         

         
        * ``upgrade_os_to`` - Specifies the desired Amazon Linux version for instances whose OS you want to upgrade, such as ``Amazon Linux 2016.09`` . You must also set the ``allow_reboot`` argument to true. 
         
        * ``allow_reboot`` - Specifies whether to allow AWS OpsWorks Stacks to reboot the instances if necessary, after installing the updates. This argument can be set to either ``true`` or ``false`` . The default value is ``false`` . 
         

         

        For example, to upgrade an instance to Amazon Linux 2016.09, set ``Args`` to the following.

         

         ``{ "upgrade_os_to":["Amazon Linux 2016.09"], "allow_reboot":["true"] }``  

        

        key -> (string)

          

          

        value -> (list)

          

          (string)

            

            

          

        

      

    Status -> (string)

      

      The deployment status:

       

       
      * running 
       
      * successful 
       
      * failed 
       

      

      

    CustomJson -> (string)

      

      A string that contains user-defined custom JSON. It can be used to override the corresponding default stack configuration attribute values for stack or to pass data to recipes. The string should be in the following format:

       

       ``"{\"key1\": \"value1\", \"key2\": \"value2\",...}"``  

       

      For more information on custom JSON, see `Use Custom JSON to Modify the Stack Configuration Attributes <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-json.html>`_ .

      

      

    InstanceIds -> (list)

      

      The IDs of the target instances.

      

      (string)

        

        

      

    

  

