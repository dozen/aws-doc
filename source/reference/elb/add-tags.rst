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

 

For more information, see `Tag Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/add-remove-tags.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/AddTags>`_


========
Synopsis
========

::

    add-tags
  --load-balancer-names <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

