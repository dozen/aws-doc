[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-traffic-policy-instance:


******************************
delete-traffic-policy-instance
******************************



===========
Description
===========



Deletes a traffic policy instance and all of the resource record sets that Amazon Route 53 created when you created the instance.

 

.. note::

   

  In the Amazon Route 53 console, traffic policy instances are known as policy records.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DeleteTrafficPolicyInstance>`_


========
Synopsis
========

::

    delete-traffic-policy-instance
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy instance that you want to delete. 

   

  .. warning::

     

    When you delete a traffic policy instance, Amazon Route 53 also deletes all of the resource record sets that were created when you created the traffic policy instance.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

