[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch describe-scaling-parameters:


***************************
describe-scaling-parameters
***************************



===========
Description
===========



Gets the scaling parameters configured for a domain. A domain's scaling parameters specify the desired search instance type and replication count. For more information, see `Configuring Scaling Options`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    describe-scaling-parameters
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ScalingParameters -> (structure)

  

  The status and configuration of a search domain's scaling parameters. 

  

  Options -> (structure)

    

    The desired instance type and desired number of replicas of each index partition.

    

    DesiredInstanceType -> (string)

      

      The instance type that you want to preconfigure for your domain. For example, ``search.m1.small`` .

      

      

    DesiredReplicationCount -> (integer)

      

      The number of replicas you want to preconfigure for each index partition.

      

      

    DesiredPartitionCount -> (integer)

      

      The number of partitions you want to preconfigure for your domain. Only valid when you select ``m2.2xlarge`` as the desired instance type.

      

      

    

  Status -> (structure)

    

    The status of domain configuration option.

    

    CreationDate -> (timestamp)

      

      A timestamp for when this option was created.

      

      

    UpdateDate -> (timestamp)

      

      A timestamp for when this option was last updated.

      

      

    UpdateVersion -> (integer)

      

      A unique integer that indicates when this option was last updated.

      

      

    State -> (string)

      

      The state of processing a change to an option. Possible values:

       

       
      * ``RequiresIndexDocuments`` : the option's latest value will not be deployed until  index-documents has been called and indexing is complete.
       
      * ``Processing`` : the option's latest value is in the process of being activated. 
       
      * ``Active`` : the option's latest value is completely deployed.
       
      * ``FailedToValidate`` : the option value is not compatible with the domain's data and cannot be used to index the data. You must either modify the option value or update or remove the incompatible documents.
       

      

      

    PendingDeletion -> (boolean)

      

      Indicates that the option will be deleted once processing is complete.

      

      

    

  



.. _Configuring Scaling Options: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-scaling-options.html
