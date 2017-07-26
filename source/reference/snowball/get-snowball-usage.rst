[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball get-snowball-usage:


******************
get-snowball-usage
******************



===========
Description
===========



Returns information about the Snowball service limit for your account, and also the number of Snowballs your account has in use.

 

The default service limit for the number of Snowballs that you can have at one time is 1. If you want to increase your service limit, contact AWS Support.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/GetSnowballUsage>`_


========
Synopsis
========

::

    get-snowball-usage
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SnowballLimit -> (integer)

  

  The service limit for number of Snowballs this account can have at once. The default service limit is 1 (one).

  

  

SnowballsInUse -> (integer)

  

  The number of Snowballs that this account is currently using.

  

  

