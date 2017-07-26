[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-instance-snapshots:


**********************
get-instance-snapshots
**********************



===========
Description
===========



Returns all instance snapshots for the user's account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetInstanceSnapshots>`_


``get-instance-snapshots`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``instanceSnapshots``


========
Synopsis
========

::

    get-instance-snapshots
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

instanceSnapshots -> (list)

  

  An array of key-value pairs containing information about the results of your get instance snapshots request.

  

  (structure)

    

    Describes the snapshot of the virtual private server, or *instance* .

    

    name -> (string)

      

      The name of the snapshot.

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the snapshot (e.g., ``arn:aws:lightsail:us-east-1:123456789101:InstanceSnapshot/d23b5706-3322-4d83-81e5-12345EXAMPLE`` ).

      

      

    supportCode -> (string)

      

      The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

      

      

    createdAt -> (timestamp)

      

      The timestamp when the snapshot was created (e.g., ``1479907467.024`` ).

      

      

    location -> (structure)

      

      The region name and availability zone where you created the snapshot.

      

      availabilityZone -> (string)

        

        The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

        

        

      regionName -> (string)

        

        The AWS Region name.

        

        

      

    resourceType -> (string)

      

      The type of resource (usually ``InstanceSnapshot`` ).

      

      

    state -> (string)

      

      The state the snapshot is in.

      

      

    progress -> (string)

      

      The progress of the snapshot.

      

      

    fromInstanceName -> (string)

      

      The instance from which the snapshot was created.

      

      

    fromInstanceArn -> (string)

      

      The Amazon Resource Name (ARN) of the instance from which the snapshot was created (e.g., ``arn:aws:lightsail:us-east-1:123456789101:Instance/64b8404c-ccb1-430b-8daf-12345EXAMPLE`` ).

      

      

    fromBlueprintId -> (string)

      

      The blueprint ID from which you created the snapshot (e.g., ``os_debian_8_3`` ). A blueprint is a virtual private server (or *instance* ) image used to create instances quickly.

      

      

    fromBundleId -> (string)

      

      The bundle ID from which you created the snapshot (e.g., ``micro_1_0`` ).

      

      

    sizeInGb -> (integer)

      

      The size in GB of the SSD.

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get instance snapshots request.

  

  

