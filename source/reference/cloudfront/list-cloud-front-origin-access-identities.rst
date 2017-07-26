[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-cloud-front-origin-access-identities:


*****************************************
list-cloud-front-origin-access-identities
*****************************************



===========
Description
===========

List origin access identities.

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
  [--generate-cli-skeleton]




=======
Options
=======

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



======
Output
======

CloudFrontOriginAccessIdentityList -> (structure)

  The CloudFrontOriginAccessIdentityList type.

  Marker -> (string)

    The value you provided for the Marker request parameter.

    

  NextMarker -> (string)

    If IsTruncated is true, this element is present and contains the value you can use for the Marker request parameter to continue listing your origin access identities where they left off.

    

  MaxItems -> (integer)

    The value you provided for the MaxItems request parameter.

    

  IsTruncated -> (boolean)

    A flag that indicates whether more origin access identities remain to be listed. If your results were truncated, you can make a follow-up pagination request using the Marker request parameter to retrieve more items in the list.

    

  Quantity -> (integer)

    The number of CloudFront origin access identities that were created by the current AWS account.

    

  Items -> (list)

    A complex type that contains one CloudFrontOriginAccessIdentitySummary element for each origin access identity that was created by the current AWS account.

    (structure)

      Summary of the information about a CloudFront origin access identity.

      Id -> (string)

        The ID for the origin access identity. For example: E74FTE3AJFJ256A.

        

      S3CanonicalUserId -> (string)

        The Amazon S3 canonical user ID for the origin access identity, which you use when giving the origin access identity read permission to an object in Amazon S3.

        

      Comment -> (string)

        The comment for this origin access identity, as originally specified when created.

        

      

    

  

