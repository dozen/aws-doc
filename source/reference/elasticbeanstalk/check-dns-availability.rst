[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk check-dns-availability:


**********************
check-dns-availability
**********************



===========
Description
===========



Checks if the specified CNAME is available.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CheckDNSAvailability>`_


========
Synopsis
========

::

    check-dns-availability
  --cname-prefix <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cname-prefix`` (string)


  The prefix used when this CNAME is reserved.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To check the availability of a CNAME**

The following command checks the availability of the subdomain ``my-cname.elasticbeanstalk.com``::

  aws elasticbeanstalk check-dns-availability --cname-prefix my-cname

Output::

  {
      "Available": true,
      "FullyQualifiedCNAME": "my-cname.elasticbeanstalk.com"
  }


======
Output
======

Available -> (boolean)

  

  Indicates if the specified CNAME is available:

   

   
  * ``true`` : The CNAME is available. 
   
  * ``false`` : The CNAME is not available. 
   

  

  

FullyQualifiedCNAME -> (string)

  

  The fully qualified CNAME to reserve when  create-environment is called with the provided prefix.

  

  

