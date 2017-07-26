[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes a tag or tags from a resource. You must provide the ARN of the resource from which you want to delete the tag or tags.



========
Synopsis
========

::

    delete-tags
  --resource-name <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-name`` (string)


  The Amazon Resource Name (ARN) from which you want to remove the tag or tags. For example, ``arn:aws:redshift:us-east-1:123456789:cluster:t1`` . 

  

``--tag-keys`` (list)


  The tag key that you want to delete.

  



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