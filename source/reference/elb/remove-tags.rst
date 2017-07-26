[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes one or more tags from the specified load balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/RemoveTags>`_


========
Synopsis
========

::

    remove-tags
  --load-balancer-names <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-names`` (list)


  The name of the load balancer. You can specify a maximum of one load balancer name.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  The list of tag keys to remove.

  



Shorthand Syntax::

    --tags Key1 Key2 Key3




JSON Syntax::

  [
    {
      "Key": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove tags from a load balancer**

This example removes a tag from the specified load balancer.

Command::

  aws elb remove-tags --load-balancer-name my-load-balancer --tags project


======
Output
======

