[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-cloud-front-origin-access-identities:


*****************************************
list-cloud-front-origin-access-identities
*****************************************



===========
Description
===========



Lists origin access identities.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/ListCloudFrontOriginAccessIdentities>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



``list-cloud-front-origin-access-identities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CloudFrontOriginAccessIdentityList.Items``


========
Synopsis
========

::

    list-cloud-front-origin-access-identities
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CloudFrontOriginAccessIdentityList -> (structure)

  

  The ``CloudFrontOriginAccessIdentityList`` type. 

  

  Marker -> (string)

    

    Use this when paginating results to indicate where to begin in your list of origin access identities. The results include identities in the list that occur after the marker. To get the next page of results, set the ``Marker`` to the value of the ``NextMarker`` from the current page's response (which is also the ID of the last identity on that page). 

    

    

  NextMarker -> (string)

    

    If ``IsTruncated`` is ``true`` , this element is present and contains the value you can use for the ``Marker`` request parameter to continue listing your origin access identities where they left off. 

    

    

  MaxItems -> (integer)

    

    The maximum number of origin access identities you want in the response body. 

    

    

  IsTruncated -> (boolean)

    

    A flag that indicates whether more origin access identities remain to be listed. If your results were truncated, you can make a follow-up pagination request using the ``Marker`` request parameter to retrieve more items in the list.

    

    

  Quantity -> (integer)

    

    The number of CloudFront origin access identities that were created by the current AWS account. 

    

    

  Items -> (list)

    

    A complex type that contains one ``CloudFrontOriginAccessIdentitySummary`` element for each origin access identity that was created by the current AWS account.

    

    (structure)

      

      Summary of the information about a CloudFront origin access identity.

      

      Id -> (string)

        

        The ID for the origin access identity. For example: ``E74FTE3AJFJ256A`` .

        

        

      S3CanonicalUserId -> (string)

        

        The Amazon S3 canonical user ID for the origin access identity, which you use when giving the origin access identity read permission to an object in Amazon S3.

        

        

      Comment -> (string)

        

        The comment for this origin access identity, as originally specified when created.

        

        

      

    

  

