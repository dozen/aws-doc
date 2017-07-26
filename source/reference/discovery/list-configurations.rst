[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery list-configurations:


*******************
list-configurations
*******************



===========
Description
===========



Retrieves a list of configuration items according to criteria that you specify in a filter. The filter criteria identifies the relationship requirements.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/ListConfigurations>`_


========
Synopsis
========

::

    list-configurations
  --configuration-type <value>
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--order-by <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-type`` (string)


  A valid configuration identified by Application Discovery Service. 

  

  Possible values:

  
  *   ``SERVER``

  
  *   ``PROCESS``

  
  *   ``CONNECTION``

  
  *   ``APPLICATION``

  

  

``--filters`` (list)


  You can filter the request using various logical operators and a *key* -*value* format. For example: 

   

   ``{"key": "serverType", "value": "webServer"}``  

   

  For a complete list of filter options and guidance about using them with this action, see `Querying Discovered Configuration Items <http://docs.aws.amazon.com/application-discovery/latest/APIReference/discovery-api-queries.html#ListConfigurations>`_ . 

  



Shorthand Syntax::

    name=string,values=string,string,condition=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "values": ["string", ...],
      "condition": "string"
    }
    ...
  ]



``--max-results`` (integer)


  The total number of items to return. The maximum value is 100.

  

``--next-token`` (string)


  Token to retrieve the next set of results. For example, if a previous call to list-configurations returned 100 items, but you set ``ListConfigurationsRequest$maxResults`` to 10, you received a set of 10 results along with a token. Use that token in this query to get the next set of 10.

  

``--order-by`` (list)


  Certain filter criteria return output that can be sorted in ascending or descending order. For a list of output characteristics for each filter, see `Using the list-configurations Action <http://docs.aws.amazon.com/application-discovery/latest/APIReference/discovery-api-queries.html#ListConfigurations>`_ .

  



Shorthand Syntax::

    fieldName=string,sortOrder=string ...




JSON Syntax::

  [
    {
      "fieldName": "string",
      "sortOrder": "ASC"|"DESC"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all of the discovered servers meeting a set of filter conditions**

This example command lists discovered servers matching either of two hostname patterns and not running Ubuntu.

Command::

  aws discovery list-configurations --configuration-type SERVER --filters name="server.hostName",values="172-31-35","172-31-42",condition="CONTAINS" name="server.osName",values="Ubuntu",condition="NOT_CONTAINS"

Output::

  {
      "configurations": [
   	{
              "server.osVersion": "3.14.48-33.39.amzn1.x86_64",
              "server.type": "EC2",
              "server.hostName": "ip-172-31-42-208",
              "server.timeOfCreation": "2016-10-28 23:44:30.0",
              "server.configurationId": "d-server-099385097ef9fbcfb",
              "server.osName": "Linux - Amazon Linux AMI release 2015.03",
              "server.agentId": "i-c142b99e"
          },
          {
              "server.osVersion": "3.14.48-33.39.amzn1.x86_64",
              "server.type": "EC2",
              "server.hostName": "ip-172-31-35-152",
              "server.timeOfCreation": "2016-10-28 23:44:00.0",
              "server.configurationId": "d-server-0c4f2dd1fee22c6c1",
              "server.osName": "Linux - Amazon Linux AMI release 2015.03",
              "server.agentId": "i-4447bc1b"
          }
      ]
  }


======
Output
======

configurations -> (list)

  

  Returns configuration details, including the configuration ID, attribute names, and attribute values.

  

  (map)

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

nextToken -> (string)

  

  Token to retrieve the next set of results. For example, if your call to list-configurations returned 100 items, but you set ``ListConfigurationsRequest$maxResults`` to 10, you received a set of 10 results along with this token. Use this token in the next query to retrieve the next set of 10.

  

  

