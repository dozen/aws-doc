[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-topics:


***********
list-topics
***********



===========
Description
===========



Returns a list of the requester's topics. Each call returns a limited list of topics, up to 100. If there are more topics, a ``NextToken`` is also returned. Use the ``NextToken`` parameter in a new ``list-topics`` call to get further results.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

