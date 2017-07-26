[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists all tags associated with a resource.



========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-arn`` (string)


  The ARN specifying the resource whose tags you want to list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

tagList -> (list)

  

  A collection of key and value pairs.

  

  (structure)

    

    A key and value pair.

     

    This data type is used as a request parameter in the  set-tags-for-resource action and a response element in the  list-tags-for-resource action.

    

    Key -> (string)

      

      The tag key.

      

      

    Value -> (string)

      

      The value assigned to a tag key.

      

      

    

  

