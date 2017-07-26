[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb select:


******
select
******



===========
Description
===========



The ``select`` operation returns a set of attributes for ``ItemNames`` that match the select expression. ``select`` is similar to the standard SQL SELECT statement. 

 

The total size of the response cannot exceed 1 MB in total size. Amazon SimpleDB automatically adjusts the number of items returned per page to enforce this limit. For example, if the client asks to retrieve 2500 items, but each individual item is 10 kB in size, the system returns 100 items and an appropriate ``NextToken`` so the client can access the next page of results. 

 

For information on how to construct select expressions, see Using select to Create Amazon SimpleDB Queries in the Developer Guide. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sdb-2009-04-15/Select>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



``select`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Items``


========
Synopsis
========

::

    select
  --select-expression <value>
  [--consistent-read | --no-consistent-read]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--select-expression`` (string)
The expression used to query the domain.

``--consistent-read`` | ``--no-consistent-read`` (boolean)
Determines whether or not strong consistency should be enforced when data is read from SimpleDB. If ``true`` , any data previously written to SimpleDB will be returned. Otherwise, results will be consistent eventually, and the client may not see data that was written immediately before your read.

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



======
Output
======

Items -> (list)

  A list of items that match the select expression.

  (structure)

    

    

    

    Name -> (string)

      The name of the item.

      

    AlternateNameEncoding -> (string)

      

      

      

      

    Attributes -> (list)

      A list of attributes.

      (structure)

        

        

        

        Name -> (string)

          The name of the attribute.

          

        AlternateNameEncoding -> (string)

          

          

          

          

        Value -> (string)

          The value of the attribute.

          

        AlternateValueEncoding -> (string)

          

          

          

          

        

      

    

  

NextToken -> (string)

  An opaque token indicating that more items than ``MaxNumberOfItems`` were matched, the response size exceeded 1 megabyte, or the execution time exceeded 5 seconds.

  

