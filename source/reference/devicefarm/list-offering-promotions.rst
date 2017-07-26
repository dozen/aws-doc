[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-offering-promotions:


************************
list-offering-promotions
************************



===========
Description
===========



Returns a list of offering promotions. Each offering promotion record contains the ID and description of the promotion. The API returns a ``NotEligible`` error if the caller is not permitted to invoke the operation. Contact `aws-devicefarm-support@amazon.com <mailto:aws-devicefarm-support@amazon.com>`_ if you believe that you should be able to invoke this operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListOfferingPromotions>`_


========
Synopsis
========

::

    list-offering-promotions
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

offeringPromotions -> (list)

  

  Information about the offering promotions.

  

  (structure)

    

    Represents information about an offering promotion.

    

    id -> (string)

      

      The ID of the offering promotion.

      

      

    description -> (string)

      

      A string describing the offering promotion.

      

      

    

  

nextToken -> (string)

  

  An identifier to be used in the next call to this operation, to return the next set of items in the list.

  

  

