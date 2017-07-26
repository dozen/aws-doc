[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains delete-tags-for-domain:


**********************
delete-tags-for-domain
**********************



===========
Description
===========



This operation deletes the specified tags for a domain.

 

All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/DeleteTagsForDomain>`_


========
Synopsis
========

::

    delete-tags-for-domain
  --domain-name <value>
  --tags-to-delete <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to delete one or more tags.

  

``--tags-to-delete`` (list)


  A list of tag keys to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

