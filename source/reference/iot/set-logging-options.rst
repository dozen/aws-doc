[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot set-logging-options:


*******************
set-logging-options
*******************



===========
Description
===========



Sets the logging options.



========
Synopsis
========

::

    set-logging-options
  --logging-options-payload <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--logging-options-payload`` (structure)


  The logging options payload.

  



Shorthand Syntax::

    roleArn=string,logLevel=string




JSON Syntax::

  {
    "roleArn": "string",
    "logLevel": "DEBUG"|"INFO"|"ERROR"|"WARN"|"DISABLED"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None