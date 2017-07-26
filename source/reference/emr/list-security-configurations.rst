[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-security-configurations:


****************************
list-security-configurations
****************************



===========
Description
===========



Lists all the security configurations visible to this account, providing their creation dates and times, and their names. This call returns a maximum of 50 clusters per call, but returns a marker to track the paging of the cluster list across multiple list-security-configurations calls.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ListSecurityConfigurations>`_


========
Synopsis
========

::

    list-security-configurations
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--marker`` (string)


  The pagination token that indicates the set of results to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list security configurations in the current region**
 
 - Command::
 
	 aws emr list-security-configurations

 - Output::

{
  "SecurityConfigurations": [
    {
      "CreationDateTime": 1473889697.417,
	  "Name": "MySecurityConfig-1"
    },
    {
	  "CreationDateTime": 1473889697.417,
      "Name": "MySecurityConfig-2"
    }
  ]
}

======
Output
======

SecurityConfigurations -> (list)

  

  The creation date and time, and name, of each security configuration.

  

  (structure)

    

    The creation date and time, and name, of a security configuration.

    

    Name -> (string)

      

      The name of the security configuration.

      

      

    CreationDateTime -> (timestamp)

      

      The date and time the security configuration was created.

      

      

    

  

Marker -> (string)

  

  A pagination token that indicates the next set of results to retrieve. Include the marker in the next ListSecurityConfiguration call to retrieve the next page of results, if required.

  

  

