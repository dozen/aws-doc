[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-thing-types:


****************
list-thing-types
****************



===========
Description
===========



Lists the existing thing types.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/ListThingTypes>`_


``list-thing-types`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``thingTypes``


========
Synopsis
========

::

    list-thing-types
  [--thing-type-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-type-name`` (string)


  The name of the thing type.

  

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

thingTypes -> (list)

  

  The thing types.

  

  (structure)

    

    The definition of the thing type, including thing type name and description.

    

    thingTypeName -> (string)

      

      The name of the thing type.

      

      

    thingTypeProperties -> (structure)

      

      The ThingTypeProperties for the thing type.

      

      thingTypeDescription -> (string)

        

        The description of the thing type.

        

        

      searchableAttributes -> (list)

        

        A list of searchable thing attribute names.

        

        (string)

          

          

        

      

    thingTypeMetadata -> (structure)

      

      The ThingTypeMetadata contains additional information about the thing type including: creation date and time, a value indicating whether the thing type is deprecated, and a date and time when it was deprecated.

      

      deprecated -> (boolean)

        

        Whether the thing type is deprecated. If **true** , no new things could be associated with this type.

        

        

      deprecationDate -> (timestamp)

        

        The date and time when the thing type was deprecated.

        

        

      creationDate -> (timestamp)

        

        The date and time when the thing type was created.

        

        

      

    

  

nextToken -> (string)

  

  The token for the next set of results, or **null** if there are no additional results.

  

  

