[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Returns a list of the tags assigned to the specified resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-type <value>
  --resource-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  Returns a list of tags for a specific resource type.

  

  Possible values:

  
  *   ``ManagedInstance``

  
  *   ``MaintenanceWindow``

  
  *   ``Parameter``

  

  

``--resource-id`` (string)


  The resource ID for which you want to see a list of tags.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the tags for a patch baseline**

This example lists the tags for a patch baseline.

Command::

  aws ssm list-tags-for-resource --resource-type "PatchBaseline" --resource-id "pb-0869b5cf84fa07081"

Output::

  {
	"TagList": [
		{
			"Value": "Project",
			"Key": "Testing"
		}
	]
  }


======
Output
======

TagList -> (list)

  

  A list of tags.

  

  (structure)

    

    Metadata that you assign to your managed instances. Tags enable you to categorize your managed instances in different ways, for example, by purpose, owner, or environment.

    

    Key -> (string)

      

      The name of the tag.

      

      

    Value -> (string)

      

      The value of the tag.

      

      

    

  

