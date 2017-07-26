[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains list-tags-for-domain:


********************
list-tags-for-domain
********************



===========
Description
===========



This operation returns all of the tags that are associated with the specified domain.

 

All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/ListTagsForDomain>`_


========
Synopsis
========

::

    list-tags-for-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to get a list of tags.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagList -> (list)

  

  A list of the tags that are associated with the specified domain.

  

  (structure)

    

    Each tag includes the following elements.

    

    Key -> (string)

      

      The key (name) of a tag.

       

      Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

       

      Constraints: Each key can be 1-128 characters long.

      

      

    Value -> (string)

      

      The value of a tag.

       

      Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

       

      Constraints: Each value can be 0-256 characters long.

      

      

    

  

