[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk check-dns-availability:


**********************
check-dns-availability
**********************



===========
Description
===========



Checks if the specified CNAME is available. 



========
Synopsis
========

::

    check-dns-availability
  --cname-prefix <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cname-prefix`` (string)


  The prefix used when this CNAME is reserved. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

