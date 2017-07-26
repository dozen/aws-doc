[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-phone-numbers-opted-out:


****************************
list-phone-numbers-opted-out
****************************



===========
Description
===========



Returns a list of phone numbers that are opted out, meaning you cannot send SMS messages to them.

 

The results for ``list-phone-numbers-opted-out`` are paginated, and each page returns up to 100 phone numbers. If additional phone numbers are available after the first page of results, then a ``NextToken`` next-token will be returned. To receive the next page, you call ``list-phone-numbers-opted-out`` again using the ``NextToken`` next-token received from the previous call. When there are no more records to return, ``NextToken`` will be null.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/ListPhoneNumbersOptedOut>`_


========
Synopsis
========

::

    list-phone-numbers-opted-out
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A ``NextToken`` next-token is used when you call the ``list-phone-numbers-opted-out`` action to retrieve additional records that are available after the first page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON next-token provided. The JSON next-token follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

phoneNumbers -> (list)

  

  A list of phone numbers that are opted out of receiving SMS messages. The list is paginated, and each page can contain up to 100 phone numbers.

  

  (string)

    

    

  

nextToken -> (string)

  

  A ``NextToken`` next-token is returned when you call the ``list-phone-numbers-opted-out`` action if additional records are available after the first page of results.

  

  

