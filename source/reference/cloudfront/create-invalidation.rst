[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront create-invalidation:


*******************
create-invalidation
*******************



===========
Description
===========

Create a new invalidation.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    create-invalidation
  --distribution-id <value>
  [--invalidation-batch <value>]
  [--paths <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--distribution-id`` (string)
The distribution's id.

``--invalidation-batch`` (structure)
The batch information for the invalidation.



Shorthand Syntax::

    Paths={Quantity=integer,Items=[string,string]},CallerReference=string




JSON Syntax::

  {
    "Paths": {
      "Quantity": integer,
      "Items": ["string", ...]
    },
    "CallerReference": "string"
  }



``--paths`` (string)
The space-separated paths to be invalidated. Note: --invalidation-batch and --paths are mututally exclusive.

``--cli-input-json`` (string)
Performs service operation based on the JSON distribution-id provided. The JSON distribution-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates an invalidation for a CloudFront distribution with the ID ``S11A16G5KZMEQD``::

  aws cloudfront create-invalidation --distribution-id S11A16G5KZMEQD \
    --paths /index.html /error.html

The --paths will automatically generate a random ``CallerReference`` every time.

Or you can use the following command to do the same thing, so that you can have a chance to specify your own ``CallerReference`` here::

  aws cloudfront create-invalidation --invalidation-batch file://invbatch.json --distribution-id S11A16G5KZMEQD

The distribution ID is available in the output of ``create-distribution`` and ``list-distributions``.

The file ``invbatch.json`` is a JSON document in the current folder that specifies two paths to invalidate::

  {
    "Paths": {
      "Quantity": 2,
      "Items": ["/index.html", "/error.html"]
    },
    "CallerReference": "my-invalidation-2015-09-01"
  }

Output of both commands::

  {
      "Invalidation": {
          "Status": "InProgress",
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
      },
      "Location": "https://cloudfront.amazonaws.com/2015-04-17/distribution/S11A16G5KZMEQD/invalidation/YNY2LI2BVJ4NJU"
  }

======
Output
======

Location -> (string)

  The fully qualified URI of the distribution and invalidation batch request, including the Invalidation ID.

  

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

      

    

  

