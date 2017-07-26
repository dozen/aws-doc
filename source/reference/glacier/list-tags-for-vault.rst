[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-tags-for-vault:


*******************
list-tags-for-vault
*******************



===========
Description
===========



This operation lists all the tags attached to a vault. The operation returns an empty map if there are no tags. For more information about tags, see `Tagging Amazon Glacier Resources <http://docs.aws.amazon.com/amazonglacier/latest/dev/tagging.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListTagsForVault>`_


========
Synopsis
========

::

    list-tags-for-vault
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command lists the tags applied to a vault named ``my-vault``::

  aws glacier list-tags-for-vault --account-id - --vault-name my-vault

Output::

  {
      "Tags": {
          "date": "july2015",
          "id": "1234"
      }
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

Tags -> (map)

  

  The tags attached to the vault. Each tag is composed of a key and a value.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

