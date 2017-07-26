[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns set-topic-attributes:


********************
set-topic-attributes
********************



===========
Description
===========



Allows a topic owner to set an attribute of the topic to a new value.



========
Synopsis
========

::

    set-topic-attributes
  --topic-arn <value>
  --attribute-name <value>
  [--attribute-value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic to modify.

  

``--attribute-name`` (string)


  The name of the attribute you want to set. Only a subset of the topic's attributes are mutable.

   

  Valid values: ``Policy`` | ``DisplayName`` | ``DeliveryPolicy`` 

  

``--attribute-value`` (string)


  The new value for the attribute.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None