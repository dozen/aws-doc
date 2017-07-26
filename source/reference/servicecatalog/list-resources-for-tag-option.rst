[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog list-resources-for-tag-option:


*****************************
list-resources-for-tag-option
*****************************



===========
Description
===========



Lists resources associated with a TagOption.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ListResourcesForTagOption>`_


========
Synopsis
========

::

    list-resources-for-tag-option
  --tag-option-id <value>
  [--resource-type <value>]
  [--page-size <value>]
  [--page-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tag-option-id`` (string)


  Identifier of the TagOption.

  

``--resource-type`` (string)


  Resource type.

  

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

ResourceDetails -> (list)

  

  The resulting detailed resource information.

  

  (structure)

    

    Detailed resource information.

    

    Id -> (string)

      

      Identifier of the resource.

      

      

    ARN -> (string)

      

      ARN of the resource.

      

      

    Name -> (string)

      

      Name of the resource.

      

      

    Description -> (string)

      

      Description of the resource.

      

      

    CreatedTime -> (timestamp)

      

      Creation time of the resource.

      

      

    

  

PageToken -> (string)

  

  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

  

