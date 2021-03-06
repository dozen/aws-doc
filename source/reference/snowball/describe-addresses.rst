[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball describe-addresses:


******************
describe-addresses
******************



===========
Description
===========



Returns a specified number of ``ADDRESS`` objects. Calling this API in one of the US regions will return addresses from the list of all addresses associated with this account in all US regions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/DescribeAddresses>`_


``describe-addresses`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Addresses``


========
Synopsis
========

::

    describe-addresses
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Addresses -> (list)

  

  The Snowball shipping addresses that were created for this account.

  

  (structure)

    

    The address that you want the Snowball or Snowballs associated with a specific job to be shipped to. Addresses are validated at the time of creation. The address you provide must be located within the serviceable area of your region. Although no individual elements of the ``Address`` are required, if the address is invalid or unsupported, then an exception is thrown.

    

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

      

      

    

  

NextToken -> (string)

  

  HTTP requests are stateless. If you use the automatically generated ``NextToken`` value in your next ``describe-addresses`` call, your list of returned addresses will start from this point in the array.

  

  

