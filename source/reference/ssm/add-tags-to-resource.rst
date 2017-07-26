[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



Adds or overwrites one or more tags for the specified resource. Tags are metadata that you assign to your managed instances, Maintenance Windows, or Parameter Store parameters. Tags enable you to categorize your resources in different ways, for example, by purpose, owner, or environment. Each tag consists of a key and an optional value, both of which you define. For example, you could define a set of tags for your account's managed instances that helps you track each instance's owner and stack level. For example: Key=Owner and Value=DbAdmin, SysAdmin, or Dev. Or Key=Stack and Value=Production, Pre-Production, or Test.

 

Each resource can have a maximum of 10 tags. 

 

We recommend that you devise a set of tag keys that meets your needs for each resource type. Using a consistent set of tag keys makes it easier for you to manage your resources. You can search and filter the resources based on the tags you add. Tags don't have any semantic meaning to Amazon EC2 and are interpreted strictly as a string of characters. 

 

For more information about tags, see `Tagging Your Amazon EC2 Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ in the *Amazon EC2 User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/AddTagsToResource>`_


========
Synopsis
========

::

    add-tags-to-resource
  --resource-type <value>
  --resource-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  Specifies the type of resource you are tagging.

  

  Possible values:

  
  *   ``ManagedInstance``

  
  *   ``MaintenanceWindow``

  
  *   ``Parameter``

  

  

``--resource-id`` (string)


  The resource ID you want to tag.

  

``--tags`` (list)


  One or more tags. The value parameter is required, but if you don't want the tag to have a value, specify the parameter with no value, and we set the value to an empty string. 

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add tags to a resource**

This example updates a maintenance window with new tags. There is no output if the command succeeds.

Command::

   aws ssm add-tags-to-resource --resource-type "MaintenanceWindow" --resource-id "mw-03eb9db42890fb82d" --tags "Key=Stack,Value=Production"


======
Output
======

