[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes metadata tags from an Amazon RDS resource.

 

For an overview on tagging an Amazon RDS resource, see `Tagging Amazon RDS Resources`_ .



========
Synopsis
========

::

    remove-tags-from-resource
  --resource-name <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-name`` (string)


  The Amazon RDS resource the tags will be removed from. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ .

  

``--tag-keys`` (list)


  The tag key (name) of the tag to be removed.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Tagging Amazon RDS Resources: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Tagging.html
.. _Constructing an RDS Amazon Resource Name (ARN): http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.html#USER_Tagging.ARN
