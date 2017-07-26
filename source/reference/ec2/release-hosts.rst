[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 release-hosts:


*************
release-hosts
*************



===========
Description
===========



When you no longer want to use an On-Demand Dedicated Host it can be released. On-Demand billing is stopped and the host goes into ``released`` state. The host ID of Dedicated Hosts that have been released can no longer be specified in another request, e.g., ModifyHosts. You must stop or terminate all instances on a host before it can be released.

 

When Dedicated Hosts are released, it make take some time for them to stop counting toward your limit and you may receive capacity errors when trying to allocate new Dedicated hosts. Try waiting a few minutes, and then try again.

 

Released hosts will still appear in a  describe-hosts response.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReleaseHosts>`_


========
Synopsis
========

::

    release-hosts
  --host-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--host-ids`` (list)


  The IDs of the Dedicated Hosts you want to release.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To release a Dedicated host from your account**

To release a Dedicated host from your account. Instances that are on the host must be stopped or terminated before the host can be released.

Command::

  aws ec2 release-hosts --host-id=h-0029d6e3cacf1b3da

Output::

  { 
      "Successful":  [
          "h-0029d6e3cacf1b3da"
           ],
    "Unsuccessful": []
    
   }


======
Output
======

Successful -> (list)

  

  The IDs of the Dedicated Hosts that were successfully released.

  

  (string)

    

    

  

Unsuccessful -> (list)

  

  The IDs of the Dedicated Hosts that could not be released, including an error message.

  

  (structure)

    

    Information about items that were not successfully processed in a batch call.

    

    Error -> (structure)

      

      Information about the error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The error message accompanying the error code.

        

        

      

    ResourceId -> (string)

      

      The ID of the resource.

      

      

    

  

