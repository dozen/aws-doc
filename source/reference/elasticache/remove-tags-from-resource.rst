[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



The *remove-tags-from-resource* action removes the tags identified by the ``TagKeys`` list from the named resource.



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


  The name of the ElastiCache resource from which you want the listed tags removed, for example ``arn:aws:elasticache:us-west-2:0123456789:cluster:myCluster`` .

  

``--tag-keys`` (list)


  A list of ``TagKeys`` identifying the tags you want removed from the named resource. For example, ``TagKeys.member.1=Region`` removes the cost allocation tag with the key name ``Region`` from the resource named by the *ResourceName* parameter.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TagList -> (list)

  

  A list of cost allocation tags as key-value pairs. 

  

  (structure)

    

    A cost allocation Tag that can be added to an ElastiCache cluster or replication group. Tags are composed of a Key/Value pair. A tag with a null Value is permitted.

    

    Key -> (string)

      

      The key for the tag.

      

      

    Value -> (string)

      

      The tag's value. May not be null.

      

      

    

  

