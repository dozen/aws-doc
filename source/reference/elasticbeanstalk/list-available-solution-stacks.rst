[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk list-available-solution-stacks:


******************************
list-available-solution-stacks
******************************



===========
Description
===========



Returns a list of the available solution stack names. 



========
Synopsis
========

::

    list-available-solution-stacks
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view solution stacks**

The following command lists solution stacks for all currently available platform configurations and any that you have used in the past::

  aws elasticbeanstalk list-available-solution-stacks

Output (abbreviated)::

  {
      "SolutionStacks": [
          "64bit Amazon Linux 2015.03 v2.0.0 running Node.js",
          "64bit Amazon Linux 2015.03 v2.0.0 running PHP 5.6",
          "64bit Amazon Linux 2015.03 v2.0.0 running PHP 5.5",
          "64bit Amazon Linux 2015.03 v2.0.0 running PHP 5.4",
          "64bit Amazon Linux 2015.03 v2.0.0 running Python 3.4",
          "64bit Amazon Linux 2015.03 v2.0.0 running Python 2.7",
          "64bit Amazon Linux 2015.03 v2.0.0 running Python",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.2 (Puma)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.2 (Passenger Standalone)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.1 (Puma)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.1 (Passenger Standalone)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.0 (Puma)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 2.0 (Passenger Standalone)",
          "64bit Amazon Linux 2015.03 v2.0.0 running Ruby 1.9.3",
          "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8",
          "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 7 Java 7",
          "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 7 Java 6",
          "64bit Windows Server Core 2012 R2 running IIS 8.5",
          "64bit Windows Server 2012 R2 running IIS 8.5",
          "64bit Windows Server 2012 running IIS 8",
          "64bit Windows Server 2008 R2 running IIS 7.5",
          "64bit Amazon Linux 2015.03 v2.0.0 running Docker 1.6.2",
          "64bit Amazon Linux 2015.03 v2.0.0 running Multi-container Docker 1.6.2 (Generic)",
          "64bit Debian jessie v2.0.0 running GlassFish 4.1 Java 8 (Preconfigured - Docker)",
          "64bit Debian jessie v2.0.0 running GlassFish 4.0 Java 7 (Preconfigured - Docker)",
          "64bit Debian jessie v2.0.0 running Go 1.4 (Preconfigured - Docker)",
          "64bit Debian jessie v2.0.0 running Go 1.3 (Preconfigured - Docker)",
          "64bit Debian jessie v2.0.0 running Python 3.4 (Preconfigured - Docker)",
      ],
      "SolutionStackDetails": [
          {
              "PermittedFileTypes": [
                  "zip"
              ],
              "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Node.js"
          },
          ...
      ]
  }



======
Output
======

SolutionStacks -> (list)

  

  A list of available solution stacks. 

  

  (string)

    

    

  

SolutionStackDetails -> (list)

  

  A list of available solution stacks and their  SolutionStackDescription . 

  

  (structure)

    

    Describes the solution stack. 

    

    SolutionStackName -> (string)

      

      The name of the solution stack. 

      

      

    PermittedFileTypes -> (list)

      

      The permitted file types allowed for a solution stack. 

      

      (string)

        

        

      

    

  

