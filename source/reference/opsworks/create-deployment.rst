[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-deployment:


*****************
create-deployment
*****************



===========
Description
===========



Runs deployment or stack commands. For more information, see `Deploying Apps`_ and `Run Stack Commands`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Deploy or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    create-deployment
  --stack-id <value>
  [--app-id <value>]
  [--instance-ids <value>]
  --command <value>
  [--comment <value>]
  [--custom-json <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--app-id`` (string)


  The app ID. This parameter is required for app deployments, but not for other deployment commands.

  

``--instance-ids`` (list)


  The instance IDs for the deployment targets.

  



Syntax::

  "string" "string" ...



``--command`` (structure)


  A ``command`` object that specifies the deployment command and any associated arguments.

  



Shorthand Syntax::

    Name=string,Args={KeyName1=string,string,KeyName2=string,string}




JSON Syntax::

  {
    "Name": "install_dependencies"|"update_dependencies"|"update_custom_cookbooks"|"execute_recipes"|"configure"|"setup"|"deploy"|"rollback"|"start"|"stop"|"restart"|"undeploy",
    "Args": {"string": ["string", ...]
      ...}
  }



``--comment`` (string)


  A user-defined comment.

  

``--custom-json`` (string)


  A string that contains user-defined, custom JSON. It is used to override the corresponding default stack configuration JSON values. The string should be in the following format and must escape characters such as '"':

   

   ``"{\"key1\": \"value1\", \"key2\": \"value2\",...}"``  

   

  For more information on custom JSON, see `Use Custom JSON to Modify the Stack Configuration Attributes`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deploy apps and run stack commands**

The following examples show how to use the ``create-deployment`` command to deploy apps and run stack commands.  Notice that the
quote (``"``) characters in the JSON object that specifies the command are all preceded by 
escape characters (\). Without the escape characters, the command might
return an invalid JSON error.

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

**Deploy an App**

The following ``create-deployment`` command deploys an app to a specified stack. ::

  aws opsworks --region us-east-1 create-deployment --stack-id cfb7e082-ad1d-4599-8e81-de1c39ab45bf --app-id 307be5c8-d55d-47b5-bd6e-7bd417c6c7eb --command "{\"Name\":\"deploy\"}"

*Output*::

  {
    "DeploymentId": "5746c781-df7f-4c87-84a7-65a119880560"
  }

**Deploy a Rails App and Migrate the Database**

The following ``create-deployment`` command deploys a Ruby on Rails app to a specified stack and migrates the
database. ::

  aws opsworks --region us-east-1 create-deployment --stack-id cfb7e082-ad1d-4599-8e81-de1c39ab45bf --app-id 307be5c8-d55d-47b5-bd6e-7bd417c6c7eb --command "{\"Name\":\"deploy\", \"Args\":{\"migrate\":[\"true\"]}}"

*Output*::

  {
    "DeploymentId": "5746c781-df7f-4c87-84a7-65a119880560"
  }

For more information on deployment, see `Deploying Apps`_ in the *AWS OpsWorks User Guide*.

**Execute a Recipe**

The following ``create-deployment`` command runs a custom recipe, ``phpapp::appsetup``, on the instances in a specified
stack. ::

  aws opsworks --region us-east-1 create-deployment --stack-id 935450cc-61e0-4b03-a3e0-160ac817d2bb --command "{\"Name\":\"execute_recipes\", \"Args\":{\"recipes\":[\"phpapp::appsetup\"]}}

*Output*::

  {
    "DeploymentId": "5cbaa7b9-4e09-4e53-aa1b-314fbd106038"
  }

For more information, see `Run Stack Commands`_ in the *AWS OpsWorks User Guide*.

**Install Dependencies**

The following ``create-deployment`` command installs dependencies, such as packages or Ruby gems, on the instances in a
specified stack. ::

  aws opsworks --region us-east-1 create-deployment --stack-id 935450cc-61e0-4b03-a3e0-160ac817d2bb --command "{\"Name\":\"install_dependencies\"}"

*Output*::

  {
    "DeploymentId": "aef5b255-8604-4928-81b3-9b0187f962ff"
  }

**More Information**

For more information, see `Run Stack Commands`_ in the *AWS OpsWorks User Guide*.

.. _`Deploying Apps`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-deploying.html
.. _`Run Stack Commands`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-commands.html



======
Output
======

DeploymentId -> (string)

  

  The deployment ID, which can be used with other requests to identify the deployment.

  

  



.. _Run Stack Commands: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-commands.html
.. _Use Custom JSON to Modify the Stack Configuration Attributes: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-json.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Deploying Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-deploying.html
