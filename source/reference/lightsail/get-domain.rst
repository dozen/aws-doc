[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-domain:


**********
get-domain
**********



===========
Description
===========



Returns information about a specific domain recordset.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetDomain>`_


========
Synopsis
========

::

    get-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain name for which your want to return information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

domain -> (structure)

  

  An array of key-value pairs containing information about your get domain request.

  

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

          

          

        

      

    

  

