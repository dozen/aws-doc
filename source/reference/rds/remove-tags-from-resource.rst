[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes metadata tags from an Amazon RDS resource.

 

For an overview on tagging an Amazon RDS resource, see `Tagging Amazon RDS Resources <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Tagging.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/RemoveTagsFromResource>`_


========
Synopsis
========

::

    remove-tags-from-resource
  --resource-name <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The Amazon RDS resource the tags will be removed from. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ .

  

``--tag-keys`` (list)


  The tag key (name) of the tag to be removed.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None