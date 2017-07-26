[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront create-invalidation:


*******************
create-invalidation
*******************



===========
Description
===========



Create a new invalidation. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/CreateInvalidation>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  The fully qualified URI of the distribution and invalidation batch request, including the ``Invalidation ID`` .

  

  

Invalidation -> (structure)

  

  The invalidation's information.

  

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

      

      

    

  

