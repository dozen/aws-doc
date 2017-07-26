[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es list-tags:


*********
list-tags
*********



===========
Description
===========



Returns all tags for the given Elasticsearch domain.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/ListTags>`_


========
Synopsis
========

::

    list-tags
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  Specify the ``arn`` for the Elasticsearch domain to which the tags are attached that you want to view.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagList -> (list)

  

  List of ``Tag`` for the requested Elasticsearch domain.

  

  (structure)

    

    Specifies a key value pair for a resource tag.

    

    Key -> (string)

      

      Specifies the ``TagKey`` , the name of the tag. Tag keys must be unique for the Elasticsearch domain to which they are attached.

      

      

    Value -> (string)

      

      Specifies the ``TagValue`` , the value assigned to the corresponding tag key. Tag values can be null and do not have to be unique in a tag set. For example, you can have a key value pair in a tag set of ``project : Trinity`` and ``cost-center : Trinity`` 

      

      

    

  

