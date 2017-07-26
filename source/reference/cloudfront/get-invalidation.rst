[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront get-invalidation:


****************
get-invalidation
****************



===========
Description
===========

Get the information about an invalidation.

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
  [--generate-cli-skeleton]




=======
Options
=======

``--distribution-id`` (string)
The distribution's id.

``--id`` (string)
The invalidation's id.

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  The invalidation's information.

  Id -> (string)

    The identifier for the invalidation request. For example: IDFDVBD632BHDS5.

    

  Status -> (string)

    The status of the invalidation request. When the invalidation batch is finished, the status is Completed.

    

  CreateTime -> (timestamp)

    The date and time the invalidation request was first made.

    

  InvalidationBatch -> (structure)

    The current invalidation information for the batch request.

    Paths -> (structure)

      The path of the object to invalidate. The path is relative to the distribution and must begin with a slash (/). You must enclose each invalidation object with the Path element tags. If the path includes non-ASCII characters or unsafe characters as defined in RFC 1783 (http://www.ietf.org/rfc/rfc1738.txt), URL encode those characters. Do not URL encode any other characters in the path, or CloudFront will not invalidate the old version of the updated object.

      Quantity -> (integer)

        The number of objects that you want to invalidate.

        

      Items -> (list)

        A complex type that contains a list of the objects that you want to invalidate.

        (string)

          

          

        

      

    CallerReference -> (string)

      A unique name that ensures the request can't be replayed. If the CallerReference is new (no matter the content of the Path object), a new distribution is created. If the CallerReference is a value you already sent in a previous request to create an invalidation batch, and the content of each Path element is identical to the original request, the response includes the same information returned to the original request. If the CallerReference is a value you already sent in a previous request to create a distribution but the content of any Path is different from the original request, CloudFront returns an InvalidationBatchAlreadyExists error.

      

    

  

