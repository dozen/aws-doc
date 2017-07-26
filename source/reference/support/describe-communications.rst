[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-communications:


***********************
describe-communications
***********************



===========
Description
===========



Returns communications (and attachments) for one or more support cases. You can use the ``afterTime`` and ``beforeTime`` parameters to filter by date. You can use the ``caseId`` parameter to restrict the results to a particular case.

 

Case data is available for 12 months after creation. If a case was created more than 12 months ago, a request for data might cause an error.

 

You can use the ``maxResults`` and ``nextToken`` parameters to control the pagination of the result set. Set ``maxResults`` to the number of cases you want displayed on each page, and use ``nextToken`` to specify the resumption of pagination.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/DescribeCommunications>`_


``describe-communications`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``communications``


========
Synopsis
========

::

    describe-communications
  --case-id <value>
  [--before-time <value>]
  [--after-time <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--case-id`` (string)


  The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47*  

  

``--before-time`` (string)


  The end date for a filtered date search on support case communications. Case communications are available for 12 months after creation.

  

``--after-time`` (string)


  The start date for a filtered date search on support case communications. Case communications are available for 12 months after creation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

communications -> (list)

  

  The communications for the case.

  

  (structure)

    

    A communication associated with an AWS Support case. The communication consists of the case ID, the message body, attachment information, the account email address, and the date and time of the communication.

    

    caseId -> (string)

      

      The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47*  

      

      

    body -> (string)

      

      The text of the communication between the customer and AWS Support.

      

      

    submittedBy -> (string)

      

      The email address of the account that submitted the AWS Support case.

      

      

    timeCreated -> (string)

      

      The time the communication was created.

      

      

    attachmentSet -> (list)

      

      Information about the attachments to the case communication.

      

      (structure)

        

        The file name and ID of an attachment to a case communication. You can use the ID to retrieve the attachment with the  describe-attachment operation.

        

        attachmentId -> (string)

          

          The ID of the attachment.

          

          

        fileName -> (string)

          

          The file name of the attachment.

          

          

        

      

    

  

nextToken -> (string)

  

  A resumption point for pagination.

  

  

