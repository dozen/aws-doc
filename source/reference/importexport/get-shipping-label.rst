[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport get-shipping-label:


******************
get-shipping-label
******************



===========
Description
===========

This operation generates a pre-paid UPS shipping label that you will use to ship your device to AWS for processing.

========
Synopsis
========

::

    get-shipping-label
  --job-ids <value>
  [--name <value>]
  [--company <value>]
  [--phone-number <value>]
  [--country <value>]
  [--state-or-province <value>]
  [--city <value>]
  [--postal-code <value>]
  [--street-1 <value>]
  [--street-2 <value>]
  [--street-3 <value>]
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-ids`` (list)




Syntax::

  "string" "string" ...



``--name`` (string)
Specifies the name of the person responsible for shipping this package.

``--company`` (string)
Specifies the name of the company that will ship this package.

``--phone-number`` (string)
Specifies the phone number of the person responsible for shipping this package.

``--country`` (string)
Specifies the name of your country for the return address.

``--state-or-province`` (string)
Specifies the name of your state or your province for the return address.

``--city`` (string)
Specifies the name of your city for the return address.

``--postal-code`` (string)
Specifies the postal code for the return address.

``--street-1`` (string)
Specifies the first part of the street address for the return address, for example 1234 Main Street.

``--street-2`` (string)
Specifies the optional second part of the street address for the return address, for example Suite 100.

``--street-3`` (string)
Specifies the optional third part of the street address for the return address, for example c/o Jane Doe.

``--api-version`` (string)
Specifies the version of the client tool.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates a pre-paid shipping label for the specified job::

  aws importexport get-shipping-label --job-ids EX1ID --name "Jane Roe" --company "Example Corp." --phone-number "206-555-1111" --country "USA" --state-or-province "WA" --city "Anytown" --postal-code "91011-1111" --street-1 "123 Any Street"

The output for the get-shipping-label command looks like the following::

  https://s3.amazonaws.com/myBucket/shipping-label-EX1ID.pdf

The link in the output contains the pre-paid shipping label generated in a PDF. It also contains shipping instructions with a unique bar code to identify and authenticate your device. For more information about using the pre-paid shipping label and shipping your device, see `Shipping Your Storage Device`_ in the *AWS Import/Export Developer Guide*.

.. _`Shipping Your Storage Device`: http://docs.aws.amazon.com/AWSImportExport/latest/DG/CHAP_ShippingYourStorageDevice.html


======
Output
======

ShippingLabelURL -> (string)

  

  

Warning -> (string)

  

  

