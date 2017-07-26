[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-subnet-group:


**********************
modify-db-subnet-group
**********************



===========
Description
===========



Modifies an existing DB subnet group. DB subnet groups must contain at least one subnet in at least two AZs in the region. 



========
Synopsis
========

::

    modify-db-subnet-group
  --db-subnet-group-name <value>
  [--db-subnet-group-description <value>]
  --subnet-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-subnet-group-name`` (string)


  The name for the DB subnet group. This value is stored as a lowercase string. 

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be "default".

   

  Example: ``mySubnetgroup`` 

  

``--db-subnet-group-description`` (string)


  The description for the DB subnet group. 

  

``--subnet-ids`` (list)


  The EC2 subnet IDs for the DB subnet group. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBSubnetGroup -> (structure)

  

  Contains the result of a successful invocation of the following actions: 

   

   
  *  create-db-subnet-group  
   
  *  modify-db-subnet-group  
   
  *  describe-db-subnet-groups  
   
  *  delete-db-subnet-group  
   

   

  This data type is used as a response element in the  describe-db-subnet-groups action.

  

  DBSubnetGroupName -> (string)

    

    The name of the DB subnet group. 

    

    

  DBSubnetGroupDescription -> (string)

    

    Provides the description of the DB subnet group. 

    

    

  VpcId -> (string)

    

    Provides the VpcId of the DB subnet group. 

    

    

  SubnetGroupStatus -> (string)

    

    Provides the status of the DB subnet group. 

    

    

  Subnets -> (list)

    

    Contains a list of  Subnet elements. 

    

    (structure)

      

      This data type is used as a response element in the  describe-db-subnet-groups action. 

      

      SubnetIdentifier -> (string)

        

        Specifies the identifier of the subnet. 

        

        

      SubnetAvailabilityZone -> (structure)

        

        Contains Availability Zone information. 

         

        This data type is used as an element in the following data type: 

        
        *  OrderableDBInstanceOption 
        

        

        

        Name -> (string)

          

          The name of the availability zone. 

          

          

        

      SubnetStatus -> (string)

        

        Specifies the status of the subnet. 

        

        

      

    

  

