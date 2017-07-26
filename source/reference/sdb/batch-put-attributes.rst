[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb batch-put-attributes:


********************
batch-put-attributes
********************



===========
Description
===========



The ``batch-put-attributes`` operation creates or replaces attributes within one or more items. By using this operation, the client can perform multiple  PutAttribute operation with a single call. This helps yield savings in round trips and latencies, enabling Amazon SimpleDB to optimize requests and generally produce better throughput. 

 

The client may specify the item name with the ``Item.X.ItemName`` parameter. The client may specify new attributes using a combination of the ``Item.X.Attribute.Y.Name`` and ``Item.X.Attribute.Y.Value`` parameters. The client may specify the first attribute for the first item using the parameters ``Item.0.Attribute.0.Name`` and ``Item.0.Attribute.0.Value`` , and for the second attribute for the first item by the parameters ``Item.0.Attribute.1.Name`` and ``Item.0.Attribute.1.Value`` , and so on. 

 

Attributes are uniquely identified within an item by their name/value combination. For example, a single item can have the attributes ``{ "first_name", "first_value" }`` and ``{ "first_name", "second_value" }`` . However, it cannot have two attribute instances where both the ``Item.X.Attribute.Y.Name`` and ``Item.X.Attribute.Y.Value`` are the same. 

 

Optionally, the requester can supply the ``Replace`` parameter for each individual value. Setting this value to ``true`` will cause the new attribute values to replace the existing attribute values. For example, if an item ``I`` has the attributes ``{ 'a', '1' }, { 'b', '2'}`` and ``{ 'b', '3' }`` and the requester does a batch-put-attributes of ``{'I', 'b', '4' }`` with the Replace parameter set to true, the final attributes of the item will be ``{ 'a', '1' }`` and ``{ 'b', '4' }`` , replacing the previous values of the 'b' attribute with the new value. 

 

.. warning::

  This operation is vulnerable to exceeding the maximum URL size when making a REST request using the HTTP GET method. This operation does not support conditions using ``Expected.X.Name`` , ``Expected.X.Value`` , or ``Expected.X.Exists`` . 

 

You can execute multiple ``batch-put-attributes`` operations and other operations in parallel. However, large numbers of concurrent ``batch-put-attributes`` calls can result in Service Unavailable (503) responses. 

 

The following limitations are enforced for this operation: 

 
* 256 attribute name-value pairs per item
 
* 1 MB request size
 
* 1 billion attributes per domain
 
* 10 GB of total user data storage per domain
 
* 25 item limit per ``batch-put-attributes`` operation
 

 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    batch-put-attributes
  --domain-name <value>
  --items <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain in which the attributes are being stored.

``--items`` (list)
A list of items on which to perform the operation.



Shorthand Syntax::

    Name=string,Attributes=[{Name=string,Value=string,Replace=boolean},{Name=string,Value=string,Replace=boolean}] ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Attributes": [
        {
          "Name": "string",
          "Value": "string",
          "Replace": true|false
        }
        ...
      ]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None