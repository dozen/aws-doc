[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-retention-policy:


********************
put-retention-policy
********************



===========
Description
===========



Sets the retention of the specified log group. A retention policy allows you to configure the number of days you want to retain log events in the specified log group. 



========
Synopsis
========

::

    put-retention-policy
  --log-group-name <value>
  --retention-in-days <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to associate the retention policy with.

  

``--retention-in-days`` (integer)


  Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command adds a 5 day retention policy to a log group named ``my-logs``::

  aws logs put-retention-policy --log-group-name my-logs --retention-in-days 5


======
Output
======

None