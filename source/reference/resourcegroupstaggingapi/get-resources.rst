[ :ref:`aws <cli:aws>` . :ref:`resourcegroupstaggingapi <cli:aws resourcegroupstaggingapi>` ]

.. _cli:aws resourcegroupstaggingapi get-resources:


*************
get-resources
*************



===========
Description
===========



Returns all the tagged resources that are associated with the specified tags (keys and values) located in the specified region for the AWS account. The tags and the resource types that you specify in the request are known as *filters* . The response includes all tags that are associated with the requested resources. If no filter is provided, this action returns a paginated resource list with the associated tags.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/resourcegroupstaggingapi-2017-01-26/GetResources>`_


``get-resources`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ResourceTagMappingList``


========
Synopsis
========

::

    get-resources
  [--tag-filters <value>]
  [--tags-per-page <value>]
  [--resource-type-filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tag-filters`` (list)


  A list of tags (keys and values). A request can include up to 50 keys, and each key can include up to 20 values.

   

  If you specify multiple filters connected by an AND operator in a single request, the response returns only those resources that are associated with every specified filter.

   

  If you specify multiple filters connected by an OR operator in a single request, the response returns all resources that are associated with at least one or possibly more of the specified filters.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--tags-per-page`` (integer)


  A limit that restricts the number of tags (key and value pairs) returned by get-resources in paginated output. A resource with no tags is counted as having one tag (one key and value pair).

   

   ``get-resources`` does not split a resource and its associated tags across pages. If the specified ``tags-per-page`` would cause such a break, a ``pagination-token`` is returned in place of the affected resource and its tags. Use that token in another request to get the remaining data. For example, if you specify a ``tags-per-page`` of ``100`` and the account has 22 resources with 10 tags each (meaning that each resource has 10 key and value pairs), the output will consist of 3 pages, with the first page displaying the first 10 resources, each with its 10 tags, the second page displaying the next 10 resources each with its 10 tags, and the third page displaying the remaining 2 resources, each with its 10 tags.

   

  

   

  You can set ``tags-per-page`` to a minimum of 100 items and the maximum of 500 items.

  

``--resource-type-filters`` (list)


  The constraints on the resources that you want returned. The format of each resource type is ``service[:resourceType]`` . For example, specifying a resource type of ``ec2`` returns all tagged Amazon EC2 resources (which includes tagged EC2 instances). Specifying a resource type of ``ec2:instance`` returns only EC2 instances. 

   

  The string for each service name and resource type is the same as that embedded in a resource's Amazon Resource Name (ARN). Consult the *AWS General Reference* for the following:

   

   
  * For a list of service name strings, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ . 
   
  * For resource type strings, see `Example ARNs <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arns-syntax>`_ . 
   
  * For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ . 
   

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PaginationToken -> (string)

  

  A string that indicates that the response contains more data than can be returned in a single response. To receive additional data, specify this string for the ``pagination-token`` value in a subsequent request.

  

  

ResourceTagMappingList -> (list)

  

  A list of resource ARNs and the tags (keys and values) associated with each.

  

  (structure)

    

    A list of resource ARNs and the tags (keys and values) that are associated with each.

    

    ResourceARN -> (string)

      

      An array of resource ARN(s).

      

      

    Tags -> (list)

      

      The tags that have been applied to one or more AWS resources.

      

      (structure)

        

        The metadata that you apply to AWS resources to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. For more information, see `Tag Basics <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-basics>`_ in the *Amazon EC2 User Guide for Linux Instances* .

        

        Key -> (string)

          

          One part of a key-value pair that make up a tag. A key is a general label that acts like a category for more specific tag values.

          

          

        Value -> (string)

          

          The optional part of a key-value pair that make up a tag. A value acts as a descriptor within a tag category (key).

          

          

        

      

    

  

