[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-invalidations:


******************
list-invalidations
******************



===========
Description
===========

List invalidation batches.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



``list-invalidations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InvalidationList.Items``


========
Synopsis
========

::

    list-invalidations
  --distribution-id <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--distribution-id`` (string)
The distribution's id.

``--max-items`` (string)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (string)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves a list of invalidations for a CloudFront web distribution with the ID ``S11A16G5KZMEQD``::

  aws cloudfront list-invalidations --distribution-id S11A16G5KZMEQD

The distribution ID is available in the output of ``create-distribution`` and ``list-distributions``.

Output::

  {
      "InvalidationList": {
          "Marker": "",
          "Items": [
              {
                  "Status": "Completed",
                  "Id": "YNY2LI2BVJ4NJU",
                  "CreateTime": "2015-08-31T21:15:52.042Z"
              }
          ],
          "IsTruncated": false,
          "MaxItems": 100,
          "Quantity": 1
      }
  }


======
Output
======

InvalidationList -> (structure)

  Information about invalidation batches.

  Marker -> (string)

    The value you provided for the Marker request parameter.

    

  NextMarker -> (string)

    If IsTruncated is true, this element is present and contains the value you can use for the Marker request parameter to continue listing your invalidation batches where they left off.

    

  MaxItems -> (integer)

    The value you provided for the MaxItems request parameter.

    

  IsTruncated -> (boolean)

    A flag that indicates whether more invalidation batch requests remain to be listed. If your results were truncated, you can make a follow-up pagination request using the Marker request parameter to retrieve more invalidation batches in the list.

    

  Quantity -> (integer)

    The number of invalidation batches that were created by the current AWS account.

    

  Items -> (list)

    A complex type that contains one InvalidationSummary element for each invalidation batch that was created by the current AWS account.

    (structure)

      Summary of an invalidation request.

      Id -> (string)

        The unique ID for an invalidation request.

        

      CreateTime -> (timestamp)

        

        

      Status -> (string)

        The status of an invalidation request.

        

      

    

  

