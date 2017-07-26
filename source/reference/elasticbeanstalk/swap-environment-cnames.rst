[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk swap-environment-cnames:


***********************
swap-environment-cnames
***********************



===========
Description
===========



Swaps the CNAMEs of two environments. 



========
Synopsis
========

::

    swap-environment-cnames
  [--source-environment-id <value>]
  [--source-environment-name <value>]
  [--destination-environment-id <value>]
  [--destination-environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-environment-id`` (string)


  The ID of the source environment. 

   

  Condition: You must specify at least the ``SourceEnvironmentID`` or the ``SourceEnvironmentName`` . You may also specify both. If you specify the ``SourceEnvironmentId`` , you must specify the ``DestinationEnvironmentId`` . 

  

``--source-environment-name`` (string)


  The name of the source environment. 

   

  Condition: You must specify at least the ``SourceEnvironmentID`` or the ``SourceEnvironmentName`` . You may also specify both. If you specify the ``SourceEnvironmentName`` , you must specify the ``DestinationEnvironmentName`` . 

  

``--destination-environment-id`` (string)


  The ID of the destination environment. 

   

  Condition: You must specify at least the ``DestinationEnvironmentID`` or the ``DestinationEnvironmentName`` . You may also specify both. You must specify the ``SourceEnvironmentId`` with the ``DestinationEnvironmentId`` . 

  

``--destination-environment-name`` (string)


  The name of the destination environment. 

   

  Condition: You must specify at least the ``DestinationEnvironmentID`` or the ``DestinationEnvironmentName`` . You may also specify both. You must specify the ``SourceEnvironmentName`` with the ``DestinationEnvironmentName`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To swap environment CNAMES**

The following command swaps the assigned subdomains of two environments::

  aws elasticbeanstalk swap-environment-cnames --source-environment-name my-env-blue --destination-environment-name my-env-green


======
Output
======

None