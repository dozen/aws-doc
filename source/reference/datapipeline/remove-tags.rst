[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes existing tags from the specified pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/RemoveTags>`_


========
Synopsis
========

::

    remove-tags
  --pipeline-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a tag from a pipeline**

This example removes the specified tag from the specified pipeline::

   aws datapipeline remove-tags --pipeline-id df-00627471SOVYZEXAMPLE --tag-keys environment


======
Output
======

