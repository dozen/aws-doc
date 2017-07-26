[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb put-attributes:


**************
put-attributes
**************



===========
Description
===========



The put-attributes operation creates or replaces attributes in an item. The client may specify new attributes using a combination of the ``Attribute.X.Name`` and ``Attribute.X.Value`` parameters. The client specifies the first attribute by the parameters ``Attribute.0.Name`` and ``Attribute.0.Value`` , the second attribute by the parameters ``Attribute.1.Name`` and ``Attribute.1.Value`` , and so on. 

 

Attributes are uniquely identified in an item by their name/value combination. For example, a single item can have the attributes ``{ "first_name", "first_value" }`` and ``{ "first_name", second_value" }`` . However, it cannot have two attribute instances where both the ``Attribute.X.Name`` and ``Attribute.X.Value`` are the same. 

 

Optionally, the requestor can supply the ``Replace`` parameter for each individual attribute. Setting this value to ``true`` causes the new attribute value to replace the existing attribute value(s). For example, if an item has the attributes ``{ 'a', '1' }`` , ``{ 'b', '2'}`` and ``{ 'b', '3' }`` and the requestor calls ``put-attributes`` using the attributes ``{ 'b', '4' }`` with the ``Replace`` parameter set to true, the final attributes of the item are changed to ``{ 'a', '1' }`` and ``{ 'b', '4' }`` , which replaces the previous values of the 'b' attribute with the new value. 

 

You cannot specify an empty string as an attribute name. 

 

Because Amazon SimpleDB makes multiple copies of client data and uses an eventual consistency update model, an immediate  get-attributes or  select operation (read) immediately after a  put-attributes or  delete-attributes operation (write) might not return the updated data. 

 

The following limitations are enforced for this operation: 

 
* 256 total attribute name-value pairs per item
 
* One billion attributes per domain
 
* 10 GB of total user data storage per domain
 

 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    put-attributes
  --domain-name <value>
  --item-name <value>
  --attributes <value>
  [--expected <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain in which to perform the operation.

``--item-name`` (string)
The name of the item.

``--attributes`` (list)
The list of attributes.



Shorthand Syntax::

    Name=string,Value=string,Replace=boolean ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string",
      "Replace": true|false
    }
    ...
  ]



``--expected`` (structure)
The update condition which, if specified, determines whether the specified attributes will be updated or not. The update condition must be satisfied in order for this request to be processed and the attributes to be updated.



Shorthand Syntax::

    Name=string,Value=string,Exists=boolean




JSON Syntax::

  {
    "Name": "string",
    "Value": "string",
    "Exists": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None