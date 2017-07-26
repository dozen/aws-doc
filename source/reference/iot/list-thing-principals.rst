[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-thing-principals:


*********************
list-thing-principals
*********************



===========
Description
===========



Lists the principals associated with the specified thing.



========
Synopsis
========

::

    list-thing-principals
  --thing-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

principals -> (list)

  

  The principals.

  

  (string)

    

    

  

