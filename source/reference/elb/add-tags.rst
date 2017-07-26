[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb add-tags:


********
add-tags
********



===========
Description
===========



Adds the specified tags to the specified load balancer. Each load balancer can have a maximum of 10 tags.

 

Each tag consists of a key and an optional value. If a tag with the same key is already associated with the load balancer, ``add-tags`` updates its value.

 

For more information, see `Tag Your Load Balancer`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    add-tags
  --load-balancer-names <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-names`` (list)


  The name of the load balancer. You can specify one load balancer only.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  The tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
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

**To add a tag to a load balancer**

This example adds tags to the specified load balancer.

Command::

  aws elb add-tags --load-balancer-name my-load-balancer --tags "Key=project,Value=lima" "Key=department,Value=digital-media"



======
Output
======



.. _Tag Your Load Balancer: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/add-remove-tags.html
