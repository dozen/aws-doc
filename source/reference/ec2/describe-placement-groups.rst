[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-placement-groups:


*************************
describe-placement-groups
*************************



===========
Description
===========



Describes one or more of your placement groups. For more information about placement groups and cluster instances, see `Cluster Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cluster_computing.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribePlacementGroups>`_


========
Synopsis
========

::

    describe-placement-groups
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--group-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``group-name`` - The name of the placement group. 
   
  * ``state`` - The state of the placement group (``pending`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``strategy`` - The strategy of the placement group (``cluster`` ). 
   

  



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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-names`` (list)


  One or more placement group names.

   

  Default: Describes all your placement groups, or only those otherwise specified.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your placement groups**

This example command describes all of your placement groups.

Command::

  aws ec2 describe-placement-groups

Output::

  {
      "PlacementGroups": [
          {
              "GroupName": "my-cluster",
              "State": "available",
              "Strategy": "cluster"
          },
          ...
      ]
  }


======
Output
======

PlacementGroups -> (list)

  

  One or more placement groups.

  

  (structure)

    

    Describes a placement group.

    

    GroupName -> (string)

      

      The name of the placement group.

      

      

    State -> (string)

      

      The state of the placement group.

      

      

    Strategy -> (string)

      

      The placement strategy.

      

      

    

  

