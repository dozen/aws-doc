[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms get-servers:


***********
get-servers
***********



===========
Description
===========

The get-servers API returns a list of all servers in your server catalog. For this call to succeed, you must previously have called ImportServerCatalog.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/GetServers>`_


``get-servers`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``serverList``


========
Synopsis
========

::

    get-servers
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
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

lastModifiedOn -> (timestamp)

  Timestamp of an operation

  

serverCatalogStatus -> (string)

  Status of Server catalog

  

serverList -> (list)

  List of servers from catalog

  (structure)

    Object representing a server

    serverId -> (string)

      Unique Identifier for a server

      

    serverType -> (string)

      Type of server.

      

    vmServer -> (structure)

      Object representing a VM server

      vmServerAddress -> (structure)

        Object representing a server's location

        vmManagerId -> (string)

          Unique Identifier for VM Manager

          

        vmId -> (string)

          Unique Identifier for a VM

          

        

      vmName -> (string)

        Name of Virtual Machine

        

      vmManagerName -> (string)

        VM Manager Name

        

      vmManagerType -> (string)

        VM Management Product

        

      vmPath -> (string)

        Path to VM

        

      

    replicationJobId -> (string)

      The unique identifier for a Replication Job.

      

    replicationJobTerminated -> (boolean)

      An indicator of the Replication Job being deleted or failed.

      

    

  

nextToken -> (string)

  Pagination token to pass as input to API call

  

