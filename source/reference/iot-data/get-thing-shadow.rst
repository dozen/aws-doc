[ :ref:`aws <cli:aws>` . :ref:`iot-data <cli:aws iot-data>` ]

.. _cli:aws iot-data get-thing-shadow:


****************
get-thing-shadow
****************



===========
Description
===========



Gets the thing shadow for the specified thing.

 

For more information, see `get-thing-shadow <http://docs.aws.amazon.com/iot/latest/developerguide/API_GetThingShadow.html>`_ in the *AWS IoT Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-data-2015-05-28/GetThingShadow>`_


.. note::

    The default endpoint data.iot.[region].amazonaws.com is intended for testing purposes only. For production code it is strongly recommended to use the custom endpoint for your account  (retrievable via the iot describe-endpoint command) to ensure best availability and reachability of the service.




========
Synopsis
========

::

    get-thing-shadow
  --thing-name <value>
  outfile <value>




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``outfile`` (string)
Filename where the content will be saved



======
Output
======

payload -> (blob)

  

  The state information, in JSON format.

  

  

