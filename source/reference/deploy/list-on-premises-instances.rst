[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-on-premises-instances:


**************************
list-on-premises-instances
**************************



===========
Description
===========



Gets a list of names for one or more on-premises instances.

 

Unless otherwise specified, both registered and deregistered on-premises instance names will be listed. To list only registered or deregistered on-premises instance names, use the registration status parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListOnPremisesInstances>`_


========
Synopsis
========

::

    list-on-premises-instances
  [--registration-status <value>]
  [--tag-filters <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registration-status`` (string)


  The registration status of the on-premises instances:

   

   
  * Deregistered: Include deregistered on-premises instances in the resulting list. 
   
  * Registered: Include registered on-premises instances in the resulting list. 
   

  

  Possible values:

  
  *   ``Registered``

  
  *   ``Deregistered``

  

  

``--tag-filters`` (list)


  The on-premises instance tags that will be used to restrict the corresponding on-premises instance names returned.

  



Shorthand Syntax::

    Key=string,Value=string,Type=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string",
      "Type": "KEY_ONLY"|"VALUE_ONLY"|"KEY_AND_VALUE"
    }
    ...
  ]



``--next-token`` (string)


  An identifier returned from the previous list on-premises instances call. It can be used to return the next set of on-premises instances in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about one or more on-premises instances**

This example gets a list of available on-premises instance names for instances that are registered in AWS CodeDeploy and also have the specified on-premises instance tag associated in AWS CodeDeploy with the instance.

Command::

  aws deploy list-on-premises-instances --registration-status Registered --tag-filters Key=Name,Value=CodeDeployDemo-OnPrem,Type=KEY_AND_VALUE

Output::

  {
    "instanceNames": [
      "AssetTag12010298EX"
    ]
  }

======
Output
======

instanceNames -> (list)

  

  The list of matching on-premises instance names.

  

  (string)

    

    

  

nextToken -> (string)

  

  If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list on-premises instances call to return the next set of on-premises instances in the list.

  

  

