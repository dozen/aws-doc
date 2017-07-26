[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-resource-data-sync:


***********************
list-resource-data-sync
***********************



===========
Description
===========



Lists your resource data sync configurations. Includes information about the last time a sync attempted to start, the last sync status, and the last time a sync successfully completed.

 

The number of sync configurations might be too large to return using a single call to ``list-resource-data-sync`` . You can limit the number of sync configurations returned by using the ``max-results`` parameter. To determine whether there are more sync configurations to list, check the value of ``next-token`` in the output. If there are more sync configurations to list, you can request them by specifying the ``next-token`` returned in the call to the parameter of a subsequent call. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListResourceDataSync>`_


========
Synopsis
========

::

    list-resource-data-sync
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A token to start the list. Use this token to get the next set of results. 

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourceDataSyncItems -> (list)

  

  A list of your current Resource Data Sync configurations and their statuses.

  

  (structure)

    

    Information about a Resource Data Sync configuration, including its current status and last successful sync.

    

    SyncName -> (string)

      

      The name of the Resource Data Sync.

      

      

    S3Destination -> (structure)

      

      Configuration information for the target Amazon S3 bucket.

      

      BucketName -> (string)

        

        The name of the Amazon S3 bucket where the aggregated data is stored.

        

        

      Prefix -> (string)

        

        An Amazon S3 prefix for the bucket.

        

        

      SyncFormat -> (string)

        

        A supported sync format. The following format is currently supported: JsonSerDe

        

        

      Region -> (string)

        

        The AWS Region with the Amazon S3 bucket targeted by the Resource Data Sync.

        

        

      

    LastSyncTime -> (timestamp)

      

      The last time the configuration attempted to sync (UTC).

      

      

    LastSuccessfulSyncTime -> (timestamp)

      

      The last time the sync operations returned a status of ``SUCCESSFUL`` (UTC).

      

      

    LastStatus -> (string)

      

      The status reported by the last sync.

      

      

    SyncCreatedTime -> (timestamp)

      

      The date and time the configuration was created (UTC).

      

      

    

  

NextToken -> (string)

  

  The token for the next set of items to return. Use this token to get the next set of results.

  

  

