[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



Adds metadata tags to an Amazon RDS resource. These tags can also be used with cost allocation reporting to track cost associated with Amazon RDS resources, or used in a Condition statement in an IAM policy for Amazon RDS.

 

For an overview on tagging Amazon RDS resources, see `Tagging Amazon RDS Resources <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Tagging.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/AddTagsToResource>`_


========
Synopsis
========

::

    add-tags-to-resource
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The Amazon RDS resource the tags will be added to. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ .

  

``--tags`` (list)


  The tags to be assigned to the Amazon RDS resource.

  



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



======
Output
======

None