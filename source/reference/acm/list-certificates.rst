[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm list-certificates:


*****************
list-certificates
*****************



===========
Description
===========



Retrieves a list of ACM Certificates and the domain name for each. You can optionally filter the list to return only the certificates that match the specified status.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/ListCertificates>`_


``list-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CertificateSummaryList``


========
Synopsis
========

::

    list-certificates
  [--certificate-statuses <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-statuses`` (list)


  The status or statuses on which to filter the list of ACM Certificates.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    PENDING_VALIDATION
    ISSUED
    INACTIVE
    EXPIRED
    VALIDATION_TIMED_OUT
    REVOKED
    FAILED





``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the ACM certificates for an AWS account**

The following ``list-certificates`` command lists the ARNs of the certificates in your account::

  aws acm list-certificates

The preceding command produces the following output::

  {
      "CertificateSummaryList": [
          {
              "CertificateArn": "arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012", 
              "DomainName": "www.example.com"
          }, 
          {
              "CertificateArn": "arn:aws:acm:us-east-1:493619779192:certificate/87654321-4321-4321-4321-210987654321", 
              "DomainName": "www.example.net"
          }
      ]
  }

You can also filter your output by using the "certificate-statuses" argument. The following command displays certificates that have a PENDING_VALIDATION status::

  aws acm list-certificates --certificate-statuses PENDING_VALIDATION

Finally, you can decide how many certificates you want to display each time you call ``list-certificates``. For example, to display no more than two certificates at a time, set the ``max-items`` argument to 2 as in the following example::

  aws acm list-certificates --max-items 2

Two certificate ARNs and a ``NextToken`` value will be displayed::

  {
      "CertificateSummaryList": [
          {
              "CertificateArn": "arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012", 
              "DomainName": "www.example.com"
          }, 
          {
              "CertificateArn": "arn:aws:acm:us-east-1:493619779192:certificate/87654321-4321-4321-4321-210987654321", 
              "DomainName": "www.example.net"
          }
      ], 
      "NextToken": "9f4d9f69-275a-41fe-b58e-2b837bd9ba48"
  }
  
To display the next two certificates in your account, set this ``NextToken`` value in your next call::

  aws acm list-certificates --max-items 2 --next-token 9f4d9f69-275a-41fe-b58e-2b837bd9ba48


======
Output
======

NextToken -> (string)

  

  When the list is truncated, this value is present and contains the value to use for the ``next-token`` parameter in a subsequent pagination request.

  

  

CertificateSummaryList -> (list)

  

  A list of ACM Certificates.

  

  (structure)

    

    This structure is returned in the response object of  list-certificates action.

    

    CertificateArn -> (string)

      

      Amazon Resource Name (ARN) of the certificate. This is of the form:

       

       ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

      

      

    DomainName -> (string)

      

      Fully qualified domain name (FQDN), such as www.example.com or example.com, for the certificate.

      

      

    

  

