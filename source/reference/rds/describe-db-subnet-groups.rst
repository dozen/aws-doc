[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-subnet-groups:


*************************
describe-db-subnet-groups
*************************



===========
Description
===========



Returns a list of DBSubnetGroup descriptions. If a DBSubnetGroupName is specified, the list will contain only the descriptions of the specified DBSubnetGroup. 

 

For an overview of CIDR ranges, go to the `Wikipedia Tutorial`_ . 



``describe-db-subnet-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBSubnetGroups``


========
Synopsis
========

::

    describe-db-subnet-groups
  [--db-subnet-group-name <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-subnet-group-name`` (string)


  The name of the DB subnet group to return details for. 

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBSubnetGroups -> (list)

  

  A list of  DBSubnetGroup instances. 

  

  (structure)

    

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

          

          

        

      

    

  



.. _Wikipedia Tutorial: http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
