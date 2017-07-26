[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 release-hosts:


*************
release-hosts
*************



===========
Description
===========



When you no longer want to use a Dedicated host it can be released. On-Demand billing is stopped and the host goes into ``released`` state. The host ID of Dedicated hosts that have been released can no longer be specified in another request, e.g., ModifyHosts. You must stop or terminate all instances on a host before it can be released.

 

When Dedicated hosts are released, it make take some time for them to stop counting toward your limit and you may receive capacity errors when trying to allocate new Dedicated hosts. Try waiting a few minutes, and then try again. 

 

Released hosts will still appear in a describe-hosts response.



========
Synopsis
========

::

    release-hosts
  --host-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--host-ids`` (list)


  The IDs of the Dedicated hosts you want to release.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  The IDs of the Dedicated hosts that were successfully released.

  

  (string)

    

    

  

Unsuccessful -> (list)

  

  The IDs of the Dedicated hosts that could not be released, including an error message.

  

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

      

      

    

  

