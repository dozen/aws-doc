[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-applications:


*****************
list-applications
*****************



===========
Description
===========



Lists the applications registered with the applicable IAM user or AWS account.



========
Synopsis
========

::

    list-applications
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  An identifier that was returned from the previous list applications call, which can be used to return the next set of applications in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about applications**

This example displays information about all applications that are associated with the user's AWS account.

Command::

  aws deploy list-applications

Output::

  {
      "applications": [
          "WordPress_App",
          "MyOther_App"
      ]
  }

======
Output
======

applications -> (list)

  

  A list of application names.

  

  (string)

    

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list applications call to return the next set of applications in the list.

  

  

