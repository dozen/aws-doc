[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes the specified tags from the specified resource.

 

To list the current tags for your resources, use  describe-tags .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/RemoveTags>`_


========
Synopsis
========

::

    remove-tags
  --resource-arns <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arns`` (list)


  The Amazon Resource Name (ARN) of the resource.

  



Syntax::

  "string" "string" ...



``--tag-keys`` (list)


  The tag keys for the tags to remove.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove tags from a load balancer**

This example removes the specified tags from the specified load balancer.

Command::

  aws elbv2 remove-tags --resource-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --tag-keys project department


======
Output
======

