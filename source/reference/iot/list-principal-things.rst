[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-principal-things:


*********************
list-principal-things
*********************



===========
Description
===========



Lists the things associated with the specified principal.



========
Synopsis
========

::

    list-principal-things
  [--next-token <value>]
  [--max-results <value>]
  --principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  A token used to retrieve the next value.

  

``--max-results`` (integer)


  The maximum number of principals to return.

  

``--principal`` (string)


  The principal.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

things -> (list)

  

  The things.

  

  (string)

    

    

  

nextToken -> (string)

  

  A token used to retrieve the next value.

  

  

