[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes tags from an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clusters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

 

The following example removes the stack tag with value Prod from a cluster:



========
Synopsis
========

::

    remove-tags
  --resource-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-id`` (string)


  The Amazon EMR resource identifier from which tags will be removed. This value must be a cluster identifier.

  

``--tag-keys`` (list)


  A list of tag keys to remove from a resource.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command removes a tag with the key ``prod`` from a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr remove-tags --resource-id j-3SD91U2E1L2QX --tag-keys prod


======
Output
======



.. _Tagging Amazon EMR Resources: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-plan-tags.html
