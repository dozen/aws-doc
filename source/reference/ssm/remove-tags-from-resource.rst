[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes all tags from the specified resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/RemoveTagsFromResource>`_


========
Synopsis
========

::

    remove-tags-from-resource
  --resource-type <value>
  --resource-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  The type of resource of which you want to remove a tag.

  

  Possible values:

  
  *   ``ManagedInstance``

  
  *   ``MaintenanceWindow``

  
  *   ``Parameter``

  

  

``--resource-id`` (string)


  The resource ID for which you want to remove tags.

  

``--tag-keys`` (list)


  Tag keys that you want to remove from the specified resource.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a tag from a patch baseline**

This example removes the tags from a patch baseline. There is no output if the command succeeds.

Command::

  aws ssm remove-tags-from-resource --resource-type "PatchBaseline" --resource-id "pb-0869b5cf84fa07081" --tag-keys "Project"


======
Output
======

