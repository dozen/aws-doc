[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes existing tags from the specified pipeline.



========
Synopsis
========

::

    remove-tags
  --pipeline-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--tag-keys`` (list)


  The keys of the tags to remove.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a tag from a pipeline**

This example removes the specified tag from the specified pipeline::

   aws datapipeline remove-tags --pipeline-id df-00627471SOVYZEXAMPLE --tag-keys environment


======
Output
======

