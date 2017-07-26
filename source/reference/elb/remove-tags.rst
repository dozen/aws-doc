[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes one or more tags from the specified load balancer.



========
Synopsis
========

::

    remove-tags
  --load-balancer-names <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

