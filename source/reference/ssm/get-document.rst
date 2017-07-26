[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-document:


************
get-document
************



===========
Description
===========



Gets the contents of the specified SSM document.



========
Synopsis
========

::

    get-document
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the contents of a configuration document**

This example gets the contents of the document called ``My_Config_Document``.

Command::

  aws ssm get-document --name "My_Config_Document"


Output::

 {
     "Content": "{\n
   \"schemaVersion\": \"1.0\",\n
   \"description\": \"Sample configuration to join an instance to a domain\",\n
   \"runtimeConfig\": {\n
     \"aws:domainJoin\": {\n
        \"properties\": [\n
          {\n
            \"directoryId\": \"d-1234567890\",\n
            \"directoryName\": \"test.example.com\",\n
            \"dnsIpAddresses\": [\"198.51.100.1\",\"198.51.100.2\"]\n
          }\n
        ]\n
     }\n
   }\n
 }", 
     "Name": "My_Config_Document"
 }

======
Output
======

Name -> (string)

  

  The name of the SSM document.

  

  

Content -> (string)

  

  The contents of the SSM document.

  

  

