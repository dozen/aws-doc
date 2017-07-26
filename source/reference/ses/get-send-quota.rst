[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-send-quota:


**************
get-send-quota
**************



===========
Description
===========



Returns the user's current sending limits.

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/GetSendQuota>`_


========
Synopsis
========

::

    get-send-quota
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get your Amazon SES sending limits**

The following example uses the ``get-send-quota`` command to return your Amazon SES sending limits::

    aws ses get-send-quota

Output::

 {
    "Max24HourSend": 200.0,
    "SentLast24Hours": 1.0,
    "MaxSendRate": 1.0
 }


Max24HourSend is your sending quota, which is the maximum number of emails that you can send in a 24-hour period.
The sending quota reflects a rolling time period. Every time you try to send an email, Amazon SES checks how many
emails you sent in the previous 24 hours. As long as the total number of emails that you have sent is less than
your quota, your send request will be accepted and your email will be sent.

SentLast24Hours is the number of emails that you have sent in the previous 24 hours.

MaxSendRate is the maximum number of emails that you can send per second.

Note that sending limits are based on recipients rather than on messages. For example, an email that has 10 recipients
counts as 10 against your sending quota.

For more information, see `Managing Your Amazon SES Sending Limits`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Managing Your Amazon SES Sending Limits`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/manage-sending-limits.html


======
Output
======

Max24HourSend -> (double)

  

  The maximum number of emails the user is allowed to send in a 24-hour interval. A value of -1 signifies an unlimited quota.

  

  

MaxSendRate -> (double)

  

  The maximum number of emails that Amazon SES can accept from the user's account per second.

   

  .. note::

     

    The rate at which Amazon SES accepts the user's messages might be less than the maximum send rate.

     

  

  

SentLast24Hours -> (double)

  

  The number of emails sent during the previous 24 hours.

  

  

