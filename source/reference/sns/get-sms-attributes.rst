[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns get-sms-attributes:


******************
get-sms-attributes
******************



===========
Description
===========



Returns the settings for sending SMS messages from your account.

 

These settings are set with the ``set-sms-attributes`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/GetSMSAttributes>`_


========
Synopsis
========

::

    get-sms-attributes
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attributes`` (list)


  A list of the individual attribute names, such as ``MonthlySpendLimit`` , for which you want values.

   

  For all attribute names, see `set-sms-attributes <http://docs.aws.amazon.com/sns/latest/api/API_SetSMSAttributes.html>`_ .

   

  If you don't use this parameter, Amazon SNS returns all SMS attributes.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

attributes -> (map)

  

  The SMS attribute names and their values.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

