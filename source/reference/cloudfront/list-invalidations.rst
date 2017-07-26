[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-invalidations:


******************
list-invalidations
******************



===========
Description
===========



Lists invalidation batches. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/ListInvalidations>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--distribution-id`` (string)


  The distribution's ID.

  

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON distribution-id provided. The JSON distribution-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The value that you provided for the ``Marker`` request parameter.

    

    

  NextMarker -> (string)

    

    If ``IsTruncated`` is ``true`` , this element is present and contains the value that you can use for the ``Marker`` request parameter to continue listing your invalidation batches where they left off.

    

    

  MaxItems -> (integer)

    

    The value that you provided for the ``MaxItems`` request parameter.

    

    

  IsTruncated -> (boolean)

    

    A flag that indicates whether more invalidation batch requests remain to be listed. If your results were truncated, you can make a follow-up pagination request using the ``Marker`` request parameter to retrieve more invalidation batches in the list.

    

    

  Quantity -> (integer)

    

    The number of invalidation batches that were created by the current AWS account. 

    

    

  Items -> (list)

    

    A complex type that contains one ``InvalidationSummary`` element for each invalidation batch created by the current AWS account.

    

    (structure)

      

      A summary of an invalidation request.

      

      Id -> (string)

        

        The unique ID for an invalidation request.

        

        

      CreateTime -> (timestamp)

        

        

      Status -> (string)

        

        The status of an invalidation request.

        

        

      

    

  

