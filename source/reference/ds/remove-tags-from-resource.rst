[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes tags from a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/RemoveTagsFromResource>`_


========
Synopsis
========

::

    remove-tags-from-resource
  --resource-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id`` (string)


  Identifier (ID) of the directory from which to remove the tag.

  

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

