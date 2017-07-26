[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-subnet-group:


**********************
create-db-subnet-group
**********************



===========
Description
===========



Creates a new DB subnet group. DB subnet groups must contain at least one subnet in at least two AZs in the region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBSubnetGroup>`_


========
Synopsis
========

::

    create-db-subnet-group
  --db-subnet-group-name <value>
  --db-subnet-group-description <value>
  --subnet-ids <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-subnet-group-name`` (string)


  The name for the DB subnet group. This value is stored as a lowercase string.

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup``  

  

``--db-subnet-group-description`` (string)


  The description for the DB subnet group.

  

``--subnet-ids`` (list)


  The EC2 Subnet IDs for the DB subnet group.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  A list of tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

        

        

      

    

  DBSubnetGroupArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB subnet group.

    

    

  

