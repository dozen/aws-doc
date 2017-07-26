[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-domains:


***********
get-domains
***********



===========
Description
===========



Returns a list of all domains in the user's account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetDomains>`_


``get-domains`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``domains``


========
Synopsis
========

::

    get-domains
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

domains -> (list)

  

  An array of key-value pairs containing information about each of the domain entries in the user's account.

  

  (structure)

    

    Describes a domain where you are storing recordsets in Lightsail.

    

    name -> (string)

      

      The name of the domain.

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the domain recordset (e.g., ``arn:aws:lightsail:global:123456789101:Domain/824cede0-abc7-4f84-8dbc-12345EXAMPLE`` ).

      

      

    supportCode -> (string)

      

      The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

      

      

    createdAt -> (timestamp)

      

      The date when the domain recordset was created.

      

      

    location -> (structure)

      

      The AWS Region and Availability Zones where the domain recordset was created.

      

      availabilityZone -> (string)

        

        The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

        

        

      regionName -> (string)

        

        The AWS Region name.

        

        

      

    resourceType -> (string)

      

      The resource type. 

      

      

    domainEntries -> (list)

      

      An array of key-value pairs containing information about the domain entries.

      

      (structure)

        

        Describes a domain recordset entry.

        

        id -> (string)

          

          The ID of the domain recordset entry.

          

          

        name -> (string)

          

          The name of the domain.

          

          

        target -> (string)

          

          The target AWS name server (e.g., ``ns-111.awsdns-22.com.`` ).

          

          

        type -> (string)

          

          The type of domain entry (e.g., ``SOA`` or ``NS`` ).

          

          

        options -> (map)

          

          The options for the domain entry.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get active names request.

  

  

