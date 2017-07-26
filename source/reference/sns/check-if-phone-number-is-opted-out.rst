[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns check-if-phone-number-is-opted-out:


**********************************
check-if-phone-number-is-opted-out
**********************************



===========
Description
===========



Accepts a phone number and indicates whether the phone holder has opted out of receiving SMS messages from your account. You cannot send SMS messages to a number that is opted out.

 

To resume sending messages, you can opt in the number by using the ``opt-in-phone-number`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/CheckIfPhoneNumberIsOptedOut>`_


========
Synopsis
========

::

    check-if-phone-number-is-opted-out
  --phone-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--phone-number`` (string)


  The phone number for which you want to check the opt out status.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

isOptedOut -> (boolean)

  

  Indicates whether the phone number is opted out:

   

   
  * ``true`` – The phone number is opted out, meaning you cannot publish SMS messages to it. 
   
  * ``false`` – The phone number is opted in, meaning you can publish SMS messages to it. 
   

  

  

