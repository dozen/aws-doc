[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball create-address:


**************
create-address
**************



===========
Description
===========



Creates an address for a Snowball to be shipped to. In most regions, addresses are validated at the time of creation. The address you provide must be located within the serviceable area of your region. If the address is invalid or unsupported, then an exception is thrown.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/CreateAddress>`_


========
Synopsis
========

::

    create-address
  --address <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--address`` (structure)


  The address that you want the Snowball shipped to.

  



Shorthand Syntax::

    AddressId=string,Name=string,Company=string,Street1=string,Street2=string,Street3=string,City=string,StateOrProvince=string,PrefectureOrDistrict=string,Landmark=string,Country=string,PostalCode=string,PhoneNumber=string,IsRestricted=boolean




JSON Syntax::

  {
    "AddressId": "string",
    "Name": "string",
    "Company": "string",
    "Street1": "string",
    "Street2": "string",
    "Street3": "string",
    "City": "string",
    "StateOrProvince": "string",
    "PrefectureOrDistrict": "string",
    "Landmark": "string",
    "Country": "string",
    "PostalCode": "string",
    "PhoneNumber": "string",
    "IsRestricted": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AddressId -> (string)

  

  The automatically generated ID for a specific address. You'll use this ID when you create a job to specify which address you want the Snowball for that job shipped to.

  

  

