[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-status:


**********
get-status
**********



===========
Description
===========

Reports the status of all of configuration recorders and delivery channels.



========
Synopsis
========

::

    get-status




=======
Options
=======

*None*


========
Examples
========

**To get the status for AWS Config**

The following command returns the status of the delivery channel and configuration recorder::

    aws configservice get-status

Output::

    Configuration Recorders:

    name: default
    recorder: ON
    last status: SUCCESS

    Delivery Channels:

    name: default
    last stream delivery status: SUCCESS
    last history delivery status: SUCCESS
    last snapshot delivery status: SUCCESS