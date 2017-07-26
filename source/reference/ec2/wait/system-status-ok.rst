[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait system-status-ok:


****************
system-status-ok
****************



===========
Description
===========

Wait until JMESPath query InstanceStatuses[].SystemStatus.Status returns ok for all elements when polling with ``describe-instance-status``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

``system-status-ok`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InstanceStatuses``


========
Synopsis
========

::

    system-status-ok
  [--dry-run | --no-dry-run]
  [--instance-ids <value>]
  [--filters <value>]
  [--include-all-instances | --no-include-all-instances]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-ids`` (list)


  One or more instance IDs.

   

  Default: Describes all your instances.

   

  Constraints: Maximum 100 explicitly specified instance IDs.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone of the instance. 
   
  * ``event.code`` - The code for the scheduled event (``instance-reboot`` | ``system-reboot`` | ``system-maintenance`` | ``instance-retirement`` | ``instance-stop`` ). 
   
  * ``event.description`` - A description of the event. 
   
  * ``event.not-after`` - The latest end time for the scheduled event (for example, ``2014-09-15T17:15:20.000Z`` ). 
   
  * ``event.not-before`` - The earliest start time for the scheduled event (for example, ``2014-09-15T17:15:20.000Z`` ). 
   
  * ``instance-state-code`` - The code for the instance state, as a 16-bit unsigned integer. The high byte is an opaque internal value and should be ignored. The low byte is set based on the state represented. The valid values are 0 (pending), 16 (running), 32 (shutting-down), 48 (terminated), 64 (stopping), and 80 (stopped). 
   
  * ``instance-state-name`` - The state of the instance (``pending`` | ``running`` | ``shutting-down`` | ``terminated`` | ``stopping`` | ``stopped`` ). 
   
  * ``instance-status.reachability`` - Filters on instance status where the name is ``reachability`` (``passed`` | ``failed`` | ``initializing`` | ``insufficient-data`` ). 
   
  * ``instance-status.status`` - The status of the instance (``ok`` | ``impaired`` | ``initializing`` | ``insufficient-data`` | ``not-applicable`` ). 
   
  * ``system-status.reachability`` - Filters on system status where the name is ``reachability`` (``passed`` | ``failed`` | ``initializing`` | ``insufficient-data`` ). 
   
  * ``system-status.status`` - The system status of the instance (``ok`` | ``impaired`` | ``initializing`` | ``insufficient-data`` | ``not-applicable`` ). 
   

  



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



``--include-all-instances`` | ``--no-include-all-instances`` (boolean)


  When ``true`` , includes the health status for all instances. When ``false`` , includes the health status for running instances only.

   

  Default: ``false`` 

  

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

None