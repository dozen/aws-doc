[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-static-ips:


**************
get-static-ips
**************



===========
Description
===========



Returns information about all static IPs in the user's account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetStaticIps>`_


``get-static-ips`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``staticIps``


========
Synopsis
========

::

    get-static-ips
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON page-token provided. The JSON page-token follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

staticIps -> (list)

  

  An array of key-value pairs containing information about your get static IPs request.

  

  (structure)

    

    Describes the static IP.

    

    name -> (string)

      

      The name of the static IP (e.g., ``StaticIP-Virginia-EXAMPLE`` ).

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the static IP (e.g., ``arn:aws:lightsail:us-east-1:123456789101:StaticIp/9cbb4a9e-f8e3-4dfe-b57e-12345EXAMPLE`` ).

      

      

    supportCode -> (string)

      

      The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

      

      

    createdAt -> (timestamp)

      

      The timestamp when the static IP was created (e.g., ``1479735304.222`` ).

      

      

    location -> (structure)

      

      The region and Availability Zone where the static IP was created.

      

      availabilityZone -> (string)

        

        The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

        

        

      regionName -> (string)

        

        The AWS Region name.

        

        

      

    resourceType -> (string)

      

      The resource type (usually ``StaticIp`` ).

      

      

    ipAddress -> (string)

      

      The static IP address.

      

      

    attachedTo -> (string)

      

      The instance where the static IP is attached (e.g., ``Amazon_Linux-1GB-Virginia-1`` ).

      

      

    isAttached -> (boolean)

      

      A Boolean value indicating whether the static IP is attached.

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get static IPs request.

  

  

