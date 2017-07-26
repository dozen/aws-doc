[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes tags from an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clusters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources <http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-plan-tags.html>`_ . 

 

The following example removes the stack tag with value Prod from a cluster:



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/RemoveTags>`_


========
Synopsis
========

::

    remove-tags
  --resource-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command removes a tag with the key ``prod`` from a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr remove-tags --resource-id j-3SD91U2E1L2QX --tag-keys prod


======
Output
======

