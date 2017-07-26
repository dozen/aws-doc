[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball describe-address:


****************
describe-address
****************



===========
Description
===========



Takes an ``address-id`` and returns specific details about that address in the form of an ``Address`` object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/DescribeAddress>`_


========
Synopsis
========

::

    describe-address
  --address-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--address-id`` (string)


  The automatically generated ID for a specific address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Address -> (structure)

  

  The address that you want the Snowball or Snowballs associated with a specific job to be shipped to.

  

  AddressId -> (string)

    

    The unique ID for an address.

    

    

  Name -> (string)

    

    The name of a person to receive a Snowball at an address.

    

    

  Company -> (string)

    

    The name of the company to receive a Snowball at an address.

    

    

  Street1 -> (string)

    

    The first line in a street address that a Snowball is to be delivered to.

    

    

  Street2 -> (string)

    

    The second line in a street address that a Snowball is to be delivered to.

    

    

  Street3 -> (string)

    

    The third line in a street address that a Snowball is to be delivered to.

    

    

  City -> (string)

    

    The city in an address that a Snowball is to be delivered to.

    

    

  StateOrProvince -> (string)

    

    The state or province in an address that a Snowball is to be delivered to.

    

    

  PrefectureOrDistrict -> (string)

    

    This field is no longer used and the value is ignored.

    

    

  Landmark -> (string)

    

    This field is no longer used and the value is ignored.

    

    

  Country -> (string)

    

    The country in an address that a Snowball is to be delivered to.

    

    

  PostalCode -> (string)

    

    The postal code in an address that a Snowball is to be delivered to.

    

    

  PhoneNumber -> (string)

    

    The phone number associated with an address that a Snowball is to be delivered to.

    

    

  IsRestricted -> (boolean)

    

    If the address you are creating is a primary address, then set this option to true. This field is not supported in most regions.

    

    

  

