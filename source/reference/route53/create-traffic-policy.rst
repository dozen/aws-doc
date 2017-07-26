[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-traffic-policy:


*********************
create-traffic-policy
*********************



===========
Description
===========



Creates a traffic policy, which you use to create multiple DNS resource record sets for one domain name (such as example.com) or one subdomain name (such as www.example.com).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateTrafficPolicy>`_


========
Synopsis
========

::

    create-traffic-policy
  --name <value>
  --document <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the traffic policy.

  

``--document`` (string)


  The definition of this traffic policy in JSON format. For more information, see `Traffic Policy Document Format <http://docs.aws.amazon.com/Route53/latest/APIReference/api-policies-traffic-policy-document-format.html>`_ .

  

``--comment`` (string)


  (Optional) Any comments that you want to include about the traffic policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicy -> (structure)

  

  A complex type that contains settings for the new traffic policy.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigned to a traffic policy when you created it.

    

    

  Version -> (integer)

    

    The version number that Amazon Route 53 assigns to a traffic policy. For a new traffic policy, the value of ``Version`` is always 1.

    

    

  Name -> (string)

    

    The name that you specified when you created the traffic policy.

    

    

  Type -> (string)

    

    The DNS type of the resource record sets that Amazon Route 53 creates when you use a traffic policy to create a traffic policy instance.

    

    

  Document -> (string)

    

    The definition of a traffic policy in JSON format. You specify the JSON document to use for a new traffic policy in the ``create-traffic-policy`` request. For more information about the JSON format, see `Traffic Policy Document Format <http://docs.aws.amazon.com/Route53/latest/APIReference/api-policies-traffic-policy-document-format.html>`_ .

    

    

  Comment -> (string)

    

    The comment that you specify in the ``create-traffic-policy`` request, if any.

    

    

  

Location -> (string)

  

  A unique URL that represents a new traffic policy.

  

  

