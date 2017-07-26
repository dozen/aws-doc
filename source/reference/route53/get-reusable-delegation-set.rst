[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-reusable-delegation-set:


***************************
get-reusable-delegation-set
***************************



===========
Description
===========



Retrieves information about a specified reusable delegation set, including the four name servers that are assigned to the delegation set.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetReusableDelegationSet>`_


========
Synopsis
========

::

    get-reusable-delegation-set
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the reusable delegation set that you want to get a list of name servers for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DelegationSet -> (structure)

  

  A complex type that contains information about the reusable delegation set.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigns to a reusable delegation set.

    

    

  CallerReference -> (string)

    

    The value that you specified for ``CallerReference`` when you created the reusable delegation set.

    

    

  NameServers -> (list)

    

    A complex type that contains a list of the authoritative name servers for a hosted zone or for a reusable delegation set.

    

    (string)

      

      

    

  

