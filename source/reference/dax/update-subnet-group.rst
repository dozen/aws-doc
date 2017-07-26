[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax update-subnet-group:


*******************
update-subnet-group
*******************



===========
Description
===========



Modifies an existing subnet group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/UpdateSubnetGroup>`_


========
Synopsis
========

::

    update-subnet-group
  --subnet-group-name <value>
  [--description <value>]
  [--subnet-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subnet-group-name`` (string)


  The name of the subnet group.

  

``--description`` (string)


  A description of the subnet group.

  

``--subnet-ids`` (list)


  A list of subnet IDs in the subnet group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SubnetGroup -> (structure)

  

  The subnet group that has been modified.

  

  SubnetGroupName -> (string)

    

    The name of the subnet group.

    

    

  Description -> (string)

    

    The description of the subnet group.

    

    

  VpcId -> (string)

    

    The Amazon Virtual Private Cloud identifier (VPC ID) of the subnet group.

    

    

  Subnets -> (list)

    

    A list of subnets associated with the subnet group. 

    

    (structure)

      

      Represents the subnet associated with a DAX cluster. This parameter refers to subnets defined in Amazon Virtual Private Cloud (Amazon VPC) and used with DAX.

      

      SubnetIdentifier -> (string)

        

        The system-assigned identifier for the subnet.

        

        

      SubnetAvailabilityZone -> (string)

        

        The Availability Zone (AZ) for subnet subnet.

        

        

      

    

  

