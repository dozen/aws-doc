[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline delete-custom-action-type:


*************************
delete-custom-action-type
*************************



===========
Description
===========



Marks a custom action as deleted. poll-for-jobs for the custom action will fail after the action is marked for deletion. Only used for custom actions.

 

.. warning::

  

  You cannot recreate a custom action after it has been deleted unless you increase the version number of the action.

  



========
Synopsis
========

::

    delete-custom-action-type
  --category <value>
  --provider <value>
  --action-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--category`` (string)


  The category of the custom action that you want to delete, such as source or deploy.

  

  Possible values:

  
  *   ``Source``

  
  *   ``Build``

  
  *   ``Deploy``

  
  *   ``Test``

  
  *   ``Invoke``

  

  

``--provider`` (string)


  The provider of the service used in the custom action, such as AWS CodeDeploy.

  

``--action-version`` (string)


  The version of the custom action to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a custom action**

This example deletes a custom action in AWS CodePipeline by using an already-created JSON file (here named DeleteMyCustomAction.json) that contains the action type, provider name, and version number of the action to be deleted. Use the list-action-types command to view the correct values for category, version, and provider.

Command::

  aws codepipeline delete-custom-action-type --cli-input-json file://DeleteMyCustomAction.json
  
JSON file sample contents::
  
  {
    "category": "Build",
    "version": "1",
    "provider": "MyJenkinsProviderName"
  }

Output::

  None.

======
Output
======

None