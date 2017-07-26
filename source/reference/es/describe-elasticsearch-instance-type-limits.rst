[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es describe-elasticsearch-instance-type-limits:


*******************************************
describe-elasticsearch-instance-type-limits
*******************************************



===========
Description
===========



Describe Elasticsearch Limits for a given InstanceType and ElasticsearchVersion. When modifying existing Domain, specify the ``  domain-name `` to know what Limits are supported for modifying. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/DescribeElasticsearchInstanceTypeLimits>`_


========
Synopsis
========

::

    describe-elasticsearch-instance-type-limits
  [--domain-name <value>]
  --instance-type <value>
  --elasticsearch-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  domain-name represents the name of the Domain that we are trying to modify. This should be present only if we are querying for Elasticsearch ``  Limits `` for existing domain. 

  

``--instance-type`` (string)


  The instance type for an Elasticsearch cluster for which Elasticsearch ``  Limits `` are needed. 

  

  Possible values:

  
  *   ``m3.medium.elasticsearch``

  
  *   ``m3.large.elasticsearch``

  
  *   ``m3.xlarge.elasticsearch``

  
  *   ``m3.2xlarge.elasticsearch``

  
  *   ``m4.large.elasticsearch``

  
  *   ``m4.xlarge.elasticsearch``

  
  *   ``m4.2xlarge.elasticsearch``

  
  *   ``m4.4xlarge.elasticsearch``

  
  *   ``m4.10xlarge.elasticsearch``

  
  *   ``t2.micro.elasticsearch``

  
  *   ``t2.small.elasticsearch``

  
  *   ``t2.medium.elasticsearch``

  
  *   ``r3.large.elasticsearch``

  
  *   ``r3.xlarge.elasticsearch``

  
  *   ``r3.2xlarge.elasticsearch``

  
  *   ``r3.4xlarge.elasticsearch``

  
  *   ``r3.8xlarge.elasticsearch``

  
  *   ``i2.xlarge.elasticsearch``

  
  *   ``i2.2xlarge.elasticsearch``

  
  *   ``d2.xlarge.elasticsearch``

  
  *   ``d2.2xlarge.elasticsearch``

  
  *   ``d2.4xlarge.elasticsearch``

  
  *   ``d2.8xlarge.elasticsearch``

  
  *   ``c4.large.elasticsearch``

  
  *   ``c4.xlarge.elasticsearch``

  
  *   ``c4.2xlarge.elasticsearch``

  
  *   ``c4.4xlarge.elasticsearch``

  
  *   ``c4.8xlarge.elasticsearch``

  
  *   ``r4.large.elasticsearch``

  
  *   ``r4.xlarge.elasticsearch``

  
  *   ``r4.2xlarge.elasticsearch``

  
  *   ``r4.4xlarge.elasticsearch``

  
  *   ``r4.8xlarge.elasticsearch``

  
  *   ``r4.16xlarge.elasticsearch``

  

  

``--elasticsearch-version`` (string)


  Version of Elasticsearch for which ``  Limits `` are needed. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

LimitsByRole -> (map)

  

  Map of Role of the Instance and Limits that are applicable. Role performed by given Instance in Elasticsearch can be one of the following: 

   
  * Data: If the given InstanceType is used as Data node
   
  * Master: If the given InstanceType is used as Master node
   

   

  

  key -> (string)

    

    

  value -> (structure)

    

    Limits for given InstanceType and for each of it's role. Limits contains following ``  StorageTypes, ``  ``  InstanceLimits `` and ``  AdditionalLimits ``  

    

    StorageTypes -> (list)

      

      StorageType represents the list of storage related types and attributes that are available for given InstanceType. 

      

      (structure)

        

        StorageTypes represents the list of storage related types and their attributes that are available for given InstanceType. 

        

        StorageTypeName -> (string)

          

          Type of the storage. List of available storage options: 

           
          * instance
          Inbuilt storage available for the given Instance 
          * ebs
          Elastic block storage that would be attached to the given Instance 

           

          

          

        StorageSubTypeName -> (string)

          

          SubType of the given storage type. List of available sub-storage options: For "instance" storageType we wont have any storageSubType, in case of "ebs" storageType we will have following valid storageSubTypes 

           
          * standard
           
          * gp2
           
          * io1
           

          Refer `` VolumeType`` for more information regarding above EBS storage options. 

          

          

        StorageTypeLimits -> (list)

          

          List of limits that are applicable for given storage type. 

          

          (structure)

            

            Limits that are applicable for given storage type. 

            

            LimitName -> (string)

              

              Name of storage limits that are applicable for given storage type. If ``  StorageType `` is ebs, following storage options are applicable 

               
              * MinimumVolumeSize
              Minimum amount of volume size that is applicable for given storage type.It can be empty if it is not applicable. 
              * MaximumVolumeSize
              Maximum amount of volume size that is applicable for given storage type.It can be empty if it is not applicable. 
              * MaximumIops
              Maximum amount of Iops that is applicable for given storage type.It can be empty if it is not applicable. 
              * MinimumIops
              Minimum amount of Iops that is applicable for given storage type.It can be empty if it is not applicable. 

               

              

              

            LimitValues -> (list)

              

              Values for the ``  StorageTypeLimit$LimitName `` . 

              

              (string)

                

                

              

            

          

        

      

    InstanceLimits -> (structure)

      

      InstanceLimits represents the list of instance related attributes that are available for given InstanceType. 

      

      InstanceCountLimits -> (structure)

        

        InstanceCountLimits represents the limits on number of instances that be created in Amazon Elasticsearch for given InstanceType. 

        

        MinimumInstanceCount -> (integer)

          

          Minimum number of Instances that can be instantiated for given InstanceType. 

          

          

        MaximumInstanceCount -> (integer)

          

          Maximum number of Instances that can be instantiated for given InstanceType. 

          

          

        

      

    AdditionalLimits -> (list)

      

      List of additional limits that are specific to a given InstanceType and for each of it's ``  InstanceRole `` . 

      

      (structure)

        

        List of limits that are specific to a given InstanceType and for each of it's ``  InstanceRole `` . 

        

        LimitName -> (string)

          

          Name of Additional Limit is specific to a given InstanceType and for each of it's ``  InstanceRole `` etc. Attributes and their details:  

           
          * MaximumNumberOfDataNodesSupported
          This attribute will be present in Master node only to specify how much data nodes upto which given ``  instance-type `` can support as master node. 
          * MaximumNumberOfDataNodesWithoutMasterNode
          This attribute will be present in Data node only to specify how much data nodes of given ``  instance-type `` upto which you don't need any master nodes to govern them. 

           

          

          

        LimitValues -> (list)

          

          Value for given ``  AdditionalLimit$LimitName `` . 

          

          (string)

            

            

          

        

      

    

  

