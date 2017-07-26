[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-topics:


***********
list-topics
***********



===========
Description
===========



Returns a list of the requester's topics. Each call returns a limited list of topics, up to 100. If there are more topics, a ``NextToken`` is also returned. Use the ``NextToken`` parameter in a new ``list-topics`` call to get further results.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/ListTopics>`_


``list-topics`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Topics``


========
Synopsis
========

::

    list-topics
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves a list of SNS topics::

  aws sns list-topics

Output::

  {
      "Topics": [
          {
              "TopicArn": "arn:aws:sns:us-west-2:0123456789012:my-topic"
          }
      ]
  }


======
Output
======

Topics -> (list)

  

  A list of topic ARNs.

  

  (structure)

    

    A wrapper type for the topic's Amazon Resource Name (ARN). To retrieve a topic's attributes, use ``get-topic-attributes`` .

    

    TopicArn -> (string)

      

      The topic's ARN.

      

      

    

  

NextToken -> (string)

  

  Token to pass along to the next ``list-topics`` request. This element is returned if there are additional topics to retrieve.

  

  

