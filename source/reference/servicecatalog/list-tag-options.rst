[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog list-tag-options:


****************
list-tag-options
****************



===========
Description
===========



Lists detailed TagOptions information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ListTagOptions>`_


========
Synopsis
========

::

    list-tag-options
  [--filters <value>]
  [--page-size <value>]
  [--page-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (structure)


  The list of filters with which to limit search results. If no search filters are specified, the output is all TagOptions. 

  



Shorthand Syntax::

    Key=string,Value=string,Active=boolean




JSON Syntax::

  {
    "Key": "string",
    "Value": "string",
    "Active": true|false
  }



``--page-size`` (integer)


  The maximum number of items to return in the results. If more results exist than fit in the specified ``page-size`` , the value of ``NextPageToken`` in the response is non-null.

  

``--page-token`` (string)


  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagOptionDetails -> (list)

  

  The resulting detailed TagOption information.

  

  (structure)

    

    The TagOption details.

    

    Key -> (string)

      

      The TagOptionDetail key.

      

      

    Value -> (string)

      

      The TagOptionDetail value.

      

      

    Active -> (boolean)

      

      The TagOptionDetail active state.

      

      

    Id -> (string)

      

      The TagOptionDetail identifier.

      

      

    

  

PageToken -> (string)

  

  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

  

