[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 add-tags:


********
add-tags
********



===========
Description
===========



Adds the specified tags to the specified resource. You can tag your Application Load Balancers and your target groups.

 

Each tag consists of a key and an optional value. If a resource already has a tag with the same key, ``add-tags`` updates its value.

 

To list the current tags for your resources, use  describe-tags . To remove tags from your resources, use  remove-tags .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/AddTags>`_


========
Synopsis
========

::

    add-tags
  --resource-arns <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arns`` (list)


  The Amazon Resource Name (ARN) of the resource.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  The tags. Each resource can have a maximum of 10 tags.

  



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

**To add tags to a load balancer**

This example adds the specified tags to the specified load balancer.

Command::

  aws elbv2 add-tags --resource-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --tags "Key=project,Value=lima" "Key=department,Value=digital-media"


======
Output
======

