[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-clusters:


*************
list-clusters
*************



===========
Description
===========



Provides the status of all clusters visible to this AWS account. Allows you to filter the list of clusters based on certain criteria; for example, filtering by cluster creation date and time or by status. This call returns a maximum of 50 clusters per call, but returns a marker to track the paging of the cluster list across multiple list-clusters calls.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ListClusters>`_


``list-clusters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Clusters``


========
Synopsis
========

::

    list-clusters
  [--created-after <value>]
  [--created-before <value>]
  [--cluster-states <value>]
  [--active | --terminated | --failed]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--created-after`` (timestamp)


  The creation date and time beginning value filter for listing clusters. For example, 2014-07-15T00:01:30. 

  

``--created-before`` (timestamp)


  The creation date and time end value filter for listing clusters. For example, 2014-07-15T00:01:30. 

  

``--cluster-states`` (string)


  The cluster state filters to apply when listing clusters.

  

  Syntax:"string" "string" ...

  

  Where valid values are:

  
  * STARTING
  
  * BOOTSTRAPPING
  
  * RUNNING
  
  * WAITING
  
  * TERMINATING
  
  * TERMINATED
  
  * TERMINATED_WITH_ERRORS
  

``--active`` | ``--terminated`` | ``--failed`` (boolean)


  Shortcut option for --cluster-states. 

  
  * --active filters clusters in 'STARTING','BOOTSTRAPPING','RUNNING','WAITING', or 'TERMINATING' states. 
  
  * --terminated filters clusters in 'TERMINATED' state. 
  
  * --failed filters clusters in 'TERMINATED_WITH_ERRORS' state. 
  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command lists all active EMR clusters in the current region::

  aws emr list-clusters --active

Output::

  {
      "Clusters": [
          {
              "Status": {
                  "Timeline": {
                      "ReadyDateTime": 1433200405.353,
                      "CreationDateTime": 1433199926.596
                  },
                  "State": "WAITING",
                  "StateChangeReason": {
                      "Message": "Waiting after step completed"
                  }
              },
              "NormalizedInstanceHours": 6,
              "Id": "j-3SD91U2E1L2QX",
              "Name": "my-cluster"
          }
      ]
  }


======
Output
======

Clusters -> (list)

  

  The list of clusters for the account based on the given filters.

  

  (structure)

    

    The summary description of the cluster.

    

    Id -> (string)

      

      The unique identifier for the cluster.

      

      

    Name -> (string)

      

      The name of the cluster.

      

      

    Status -> (structure)

      

      The details about the current status of the cluster.

      

      State -> (string)

        

        The current state of the cluster.

        

        

      StateChangeReason -> (structure)

        

        The reason for the cluster status change.

        

        Code -> (string)

          

          The programmatic code for the state change reason.

          

          

        Message -> (string)

          

          The descriptive message for the state change reason.

          

          

        

      Timeline -> (structure)

        

        A timeline that represents the status of a cluster over the lifetime of the cluster.

        

        CreationDateTime -> (timestamp)

          

          The creation date and time of the cluster.

          

          

        ReadyDateTime -> (timestamp)

          

          The date and time when the cluster was ready to execute steps.

          

          

        EndDateTime -> (timestamp)

          

          The date and time when the cluster was terminated.

          

          

        

      

    NormalizedInstanceHours -> (integer)

      

      An approximation of the cost of the cluster, represented in m1.small/hours. This value is incremented one time for every hour an m1.small instance runs. Larger instances are weighted more, so an EC2 instance that is roughly four times more expensive would result in the normalized instance hours being incremented by four. This result is only an approximation and does not reflect the actual billing rate.

      

      

    

  

Marker -> (string)

  

  The pagination token that indicates the next set of results to retrieve.

  

  

