[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes the specified set of tags from the specified Elasticsearch domain.



========
Synopsis
========

::

    remove-tags
  --arn <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  Specifies the ``arn`` for the Elasticsearch domain from which you want to delete the specified tags.

  

``--tag-keys`` (list)


  Specifies the ``TagKey`` list which you want to remove from the Elasticsearch domain.

  



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