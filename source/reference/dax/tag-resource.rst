[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax tag-resource:


************
tag-resource
************



===========
Description
===========



Associates a set of tags with a DAX resource. You can call ``tag-resource`` up to 5 times per second, per account. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/TagResource>`_


========
Synopsis
========

::

    tag-resource
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The name of the DAX resource to which tags should be added.

  

``--tags`` (list)


  The tags to be assigned to the DAX resource. 

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  The list of tags that are associated with the DAX resource.

  

  (structure)

    

    A description of a tag. Every tag is a key-value pair. You can add up to 50 tags to a single DAX cluster.

     

    AWS-assigned tag names and values are automatically assigned the ``aws:`` prefix, which the user cannot assign. AWS-assigned tag names do not count towards the tag limit of 50. User-assigned tag names have the prefix ``user:`` .

     

    You cannot backdate the application of a tag.

    

    Key -> (string)

      

      The key for the tag. Tag keys are case sensitive. Every DAX cluster can only have one tag with the same key. If you try to add an existing tag (same key), the existing tag value will be updated to the new value.

      

      

    Value -> (string)

      

      The value of the tag. Tag values are case-sensitive and can be null. 

      

      

    

  

