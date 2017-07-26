[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront get-invalidation:


****************
get-invalidation
****************



===========
Description
===========



Get the information about an invalidation. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/GetInvalidation>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    get-invalidation
  --distribution-id <value>
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--distribution-id`` (string)


  The distribution's ID.

  

``--id`` (string)


  The identifier for the invalidation request, for example, ``IDFDVBD632BHDS5`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON distribution-id provided. The JSON distribution-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves an invalidation with the ID ``YNY2LI2BVJ4NJU`` for a CloudFront web distribution with the ID ``S11A16G5KZMEQD``::

  aws cloudfront get-invalidation --id YNY2LI2BVJ4NJU --distribution-id S11A16G5KZMEQD

The distribution ID is available in the output of ``create-distribution`` and ``list-distributions``. The invalidation ID is available in the output of ``create-invalidation`` and ``list-invalidations``.

Output::

  {
      "Invalidation": {
          "Status": "Completed",
          "InvalidationBatch": {
              "Paths": {
                  "Items": [
                      "/index.html",
                      "/error.html"
                  ],
                  "Quantity": 2
              },
              "CallerReference": "my-invalidation-2015-09-01"
          },
          "Id": "YNY2LI2BVJ4NJU",
          "CreateTime": "2015-08-31T21:15:52.042Z"
      }
  }


======
Output
======

Invalidation -> (structure)

  

  The invalidation's information. For more information, see `Invalidation Complex Type <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/InvalidationDatatype.html>`_ . 

  

  Id -> (string)

    

    The identifier for the invalidation request. For example: ``IDFDVBD632BHDS5`` .

    

    

  Status -> (string)

    

    The status of the invalidation request. When the invalidation batch is finished, the status is ``Completed`` .

    

    

  CreateTime -> (timestamp)

    

    The date and time the invalidation request was first made. 

    

    

  InvalidationBatch -> (structure)

    

    The current invalidation information for the batch request. 

    

    Paths -> (structure)

      

      A complex type that contains information about the objects that you want to invalidate. For more information, see `Specifying the Objects to Invalidate <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html#invalidation-specifying-objects>`_ in the *Amazon CloudFront Developer Guide* . 

      

      Quantity -> (integer)

        

        The number of objects that you want to invalidate.

        

        

      Items -> (list)

        

        A complex type that contains a list of the paths that you want to invalidate.

        

        (string)

          

          

        

      

    CallerReference -> (string)

      

      A value that you specify to uniquely identify an invalidation request. CloudFront uses the value to prevent you from accidentally resubmitting an identical request. Whenever you create a new invalidation request, you must specify a new value for ``CallerReference`` and change other values in the request as applicable. One way to ensure that the value of ``CallerReference`` is unique is to use a ``timestamp`` , for example, ``20120301090000`` .

       

      If you make a second invalidation request with the same value for ``CallerReference`` , and if the rest of the request is the same, CloudFront doesn't create a new invalidation request. Instead, CloudFront returns information about the invalidation request that you previously created with the same ``CallerReference`` .

       

      If ``CallerReference`` is a value you already sent in a previous invalidation batch request but the content of any ``Path`` is different from the original request, CloudFront returns an ``InvalidationBatchAlreadyExists`` error.

      

      

    

  

