[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb delete-attributes:


*****************
delete-attributes
*****************



===========
Description
===========



Deletes one or more attributes associated with an item. If all attributes of the item are deleted, the item is deleted. 

 

 ``delete-attributes`` is an idempotent operation; running it multiple times on the same item or attribute does not result in an error response. 

 

Because Amazon SimpleDB makes multiple copies of item data and uses an eventual consistency update model, performing a  get-attributes or  select operation (read) immediately after a ``delete-attributes`` or  put-attributes operation (write) might not return updated item data. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    delete-attributes
  --domain-name <value>
  --item-name <value>
  [--attributes <value>]
  [--expected <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain in which to perform the operation.

``--item-name`` (string)
The name of the item. Similar to rows on a spreadsheet, items represent individual objects that contain one or more value-attribute pairs.

``--attributes`` (list)
A list of Attributes. Similar to columns on a spreadsheet, attributes represent categories of data that can be assigned to items.



Shorthand Syntax::

    Name=string,AlternateNameEncoding=string,Value=string,AlternateValueEncoding=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "AlternateNameEncoding": "string",
      "Value": "string",
      "AlternateValueEncoding": "string"
    }
    ...
  ]



``--expected`` (structure)
The update condition which, if specified, determines whether the specified attributes will be deleted or not. The update condition must be satisfied in order for this request to be processed and the attributes to be deleted.



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