[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-instances:


*************
get-instances
*************



===========
Description
===========



Returns information about all Amazon Lightsail virtual private servers, or *instances* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetInstances>`_


``get-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``instances``


========
Synopsis
========

::

    get-instances
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

instances -> (list)

  

  An array of key-value pairs containing information about your instances.

  

  (structure)

    

    Describes an instance (a virtual private server).

    

    name -> (string)

      

      The name the user gave the instance (e.g., ``Amazon_Linux-1GB-Virginia-1`` ).

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the instance (e.g., ``arn:aws:lightsail:us-east-1:123456789101:Instance/244ad76f-8aad-4741-809f-12345EXAMPLE`` ).

      

      

    supportCode -> (string)

      

      The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

      

      

    createdAt -> (timestamp)

      

      The timestamp when the instance was created (e.g., ``1479734909.17`` ).

      

      

    location -> (structure)

      

      The region name and availability zone where the instance is located.

      

      availabilityZone -> (string)

        

        The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

        

        

      regionName -> (string)

        

        The AWS Region name.

        

        

      

    resourceType -> (string)

      

      The type of resource (usually ``Instance`` ).

      

      

    blueprintId -> (string)

      

      The blueprint ID (e.g., ``os_amlinux_2016_03`` ).

      

      

    blueprintName -> (string)

      

      The friendly name of the blueprint (e.g., ``Amazon Linux`` ).

      

      

    bundleId -> (string)

      

      The bundle for the instance (e.g., ``micro_1_0`` ).

      

      

    isStaticIp -> (boolean)

      

      A Boolean value indicating whether this instance has a static IP assigned to it.

      

      

    privateIpAddress -> (string)

      

      The private IP address of the instance.

      

      

    publicIpAddress -> (string)

      

      The public IP address of the instance.

      

      

    ipv6Address -> (string)

      

      The IPv6 address of the instance.

      

      

    hardware -> (structure)

      

      The size of the vCPU and the amount of RAM for the instance.

      

      cpuCount -> (integer)

        

        The number of vCPUs the instance has.

        

        

      disks -> (list)

        

        The disks attached to the instance.

        

        (structure)

          

          Describes the hard disk (an SSD).

          

          name -> (string)

            

            The name of the disk.

            

            

          arn -> (string)

            

            The Amazon Resource Name (ARN) of the disk.

            

            

          supportCode -> (string)

            

            The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

            

            

          createdAt -> (timestamp)

            

            The date when the disk was created.

            

            

          location -> (structure)

            

            The region and Availability Zone where the disk is located.

            

            availabilityZone -> (string)

              

              The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

              

              

            regionName -> (string)

              

              The AWS Region name.

              

              

            

          resourceType -> (string)

            

            The resource type of the disk. 

            

            

          sizeInGb -> (integer)

            

            The size of the disk in GB.

            

            

          gbInUse -> (integer)

            

            The number of GB in use by the disk.

            

            

          isSystemDisk -> (boolean)

            

            A Boolean value indicating whether this disk is a system disk (has an operating system loaded on it).

            

            

          iops -> (integer)

            

            The input/output operations per second (IOPS) of the disk.

            

            

          path -> (string)

            

            The disk path.

            

            

          attachedTo -> (string)

            

            The resources to which the disk is attached.

            

            

          isAttached -> (boolean)

            

            A Boolean value indicating whether the disk is attached.

            

            

          attachmentState -> (string)

            

            The attachment state of the disk.

            

            

          

        

      ramSizeInGb -> (float)

        

        The amount of RAM in GB on the instance (e.g., ``1.0`` ).

        

        

      

    networking -> (structure)

      

      Information about the public ports and monthly data transfer rates for the instance.

      

      monthlyTransfer -> (structure)

        

        The amount of data in GB allocated for monthly data transfers.

        

        gbPerMonthAllocated -> (integer)

          

          The amount allocated per month (in GB).

          

          

        

      ports -> (list)

        

        An array of key-value pairs containing information about the ports on the instance.

        

        (structure)

          

          Describes information about the instance ports.

          

          fromPort -> (integer)

            

            The first port in the range.

            

            

          toPort -> (integer)

            

            The last port in the range.

            

            

          protocol -> (string)

            

            The protocol being used. Can be one of the following.

             

             
            * ``tcp`` - Transmission Control Protocol (TCP) provides reliable, ordered, and error-checked delivery of streamed data between applications running on hosts communicating by an IP network. If you have an application that doesn't require reliable data stream service, use UDP instead. 
             
            * ``all`` - All transport layer protocol types. For more general information, see `Transport layer <https://en.wikipedia.org/wiki/Transport_layer>`_ on Wikipedia. 
             
            * ``udp`` - With User Datagram Protocol (UDP), computer applications can send messages (or datagrams) to other hosts on an Internet Protocol (IP) network. Prior communications are not required to set up transmission channels or data paths. Applications that don't require reliable data stream service can use UDP, which provides a connectionless datagram service that emphasizes reduced latency over reliability. If you do require reliable data stream service, use TCP instead. 
             

            

            

          accessFrom -> (string)

            

            The location from which access is allowed (e.g., ``Anywhere (0.0.0.0/0)`` ).

            

            

          accessType -> (string)

            

            The type of access (``Public`` or ``Private`` ).

            

            

          commonName -> (string)

            

            The common name.

            

            

          accessDirection -> (string)

            

            The access direction (``inbound`` or ``outbound`` ).

            

            

          

        

      

    state -> (structure)

      

      The status code and the state (e.g., ``running`` ) for the instance.

      

      code -> (integer)

        

        The status code for the instance.

        

        

      name -> (string)

        

        The state of the instance (e.g., ``running`` or ``pending`` ).

        

        

      

    username -> (string)

      

      The user name for connecting to the instance (e.g., ``ec2-user`` ).

      

      

    sshKeyName -> (string)

      

      The name of the SSH key being used to connect to the instance (e.g., ``LightsailDefaultKeyPair`` ).

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get instances request.

  

  

