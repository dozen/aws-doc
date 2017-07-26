[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-endpoint:


*****************
describe-endpoint
*****************



===========
Description
===========



Returns a unique endpoint specific to the AWS account making the call. You specify the following URI when updating state information for your thing: https://*endpoint* /things/*thingName* /shadow.



========
Synopsis
========

::

    describe-endpoint
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

endpointAddress -> (string)

  

  The endpoint. The format of the endpoint is as follows: *identifier* .iot.*region* .amazonaws.com.

  

  

