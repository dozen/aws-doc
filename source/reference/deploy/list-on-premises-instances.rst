[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-on-premises-instances:


**************************
list-on-premises-instances
**************************



===========
Description
===========



Gets a list of one or more on-premises instance names.

 

Unless otherwise specified, both registered and deregistered on-premises instance names will be listed. To list only registered or deregistered on-premises instance names, use the registration status parameter.



========
Synopsis
========

::

    list-on-premises-instances
  [--registration-status <value>]
  [--tag-filters <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registration-status`` (string)


  The on-premises instances registration status:

   

   
  * Deregistered: Include in the resulting list deregistered on-premises instances.
   
  * Registered: Include in the resulting list registered on-premises instances.
   

  

  Possible values:

  
  *   ``Registered``

  
  *   ``Deregistered``

  

  

``--tag-filters`` (list)


  The on-premises instance tags that will be used to restrict the corresponding on-premises instance names that are returned.

  



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


  An identifier that was returned from the previous list on-premises instances call, which can be used to return the next set of on-premises instances in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list on-premises instances call to return the next set of on-premises instances in the list.

  

  

