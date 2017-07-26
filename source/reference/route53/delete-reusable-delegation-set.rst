[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-reusable-delegation-set:


******************************
delete-reusable-delegation-set
******************************



===========
Description
===========



Deletes a reusable delegation set.

 

.. warning::

   

  You can delete a reusable delegation set only if it isn't associated with any hosted zones.

   

 

To verify that the reusable delegation set is not associated with any hosted zones, submit a  get-reusable-delegation-set request and specify the ID of the reusable delegation set that you want to delete.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DeleteReusableDelegationSet>`_


========
Synopsis
========

::

    delete-reusable-delegation-set
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the reusable delegation set that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

