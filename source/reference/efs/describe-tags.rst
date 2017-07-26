[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-tags:


*************
describe-tags
*************



===========
Description
===========



Returns the tags associated with a file system. The order of tags returned in the response of one ``describe-tags`` call and the order of tags returned across the responses of a multi-call iteration (when using pagination) is unspecified. 

 

This operation requires permissions for the ``elasticfilesystem:DescribeTags`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DescribeTags>`_


``describe-tags`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Tags``


========
Synopsis
========

::

    describe-tags
  [--max-items <value>]
  --file-system-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--file-system-id`` (string)


  ID of the file system whose tag set you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  If the request included a ``marker`` , the response returns that value in this field.

  

  

Tags -> (list)

  

  Returns tags associated with the file system as an array of ``Tag`` objects. 

  

  (structure)

    

    A tag is a key-value pair. Allowed characters: letters, whitespace, and numbers, representable in UTF-8, and the following characters:``+ - = . _ : /``  

    

    Key -> (string)

      

      Tag key (String). The key can't start with ``aws:`` .

      

      

    Value -> (string)

      

      Value of the tag key.

      

      

    

  

NextMarker -> (string)

  

  If a value is present, there are more tags to return. In a subsequent request, you can provide the value of ``NextMarker`` as the value of the ``marker`` parameter in your next request to retrieve the next set of tags.

  

  

