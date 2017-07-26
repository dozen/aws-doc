[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr add-tags:


********
add-tags
********



===========
Description
===========



Adds tags to an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clusters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 



========
Synopsis
========

::

    add-tags
  --resource-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-id`` (string)


  The Amazon EMR resource identifier to which tags will be added. This value must be a cluster identifier.

  

``--tags`` (string)


  A list of tags to associate with a cluster and propagate to each Amazon EC2 instance in the cluster. They are user-defined key/value pairs that consist of a required key string with a maximum of 128 characters and an optional value string with a maximum of 256 characters.

  

  You can specify tags in ``key=value`` format or to add a tag without value just write key name, ``key`` .

  

  Syntax:

  

  Multiple tags separated by a space. 

  

  --tags key1=value1 key2=value2

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**1. To add tags to a cluster**

- Command::

    aws emr add-tags --resource-id j-xxxxxxx --tags name="John Doe" age=29 sex=male address="123 East NW Seattle"

- Output::

    None

**2. To list tags of a cluster**

--Command::

  aws emr describe-cluster --cluster-id j-XXXXXXYY --query Cluster.Tags

- Output::

    [
        {
            "Value": "male",
            "Key": "sex"
        },
        {
            "Value": "123 East NW Seattle",
            "Key": "address"
        },
        {
            "Value": "John Doe",
            "Key": "name"
        },
        {
            "Value": "29",
            "Key": "age"
        }
    ]


======
Output
======



.. _Tagging Amazon EMR Resources: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-plan-tags.html
