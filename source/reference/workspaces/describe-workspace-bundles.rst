[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces describe-workspace-bundles:


**************************
describe-workspace-bundles
**************************



===========
Description
===========



Obtains information about the WorkSpace bundles that are available to your account in the specified region.

 

You can filter the results with either the ``BundleIds`` parameter, or the ``Owner`` parameter, but not both.

 

This operation supports pagination with the use of the ``NextToken`` request and response parameters. If more results are available, the ``NextToken`` response member contains a token that you pass in the next call to this operation to retrieve the next set of items.



========
Synopsis
========

::

    describe-workspace-bundles
  [--bundle-ids <value>]
  [--owner <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bundle-ids`` (list)


  An array of strings that contains the identifiers of the bundles to retrieve. This parameter cannot be combined with any other filter parameter.

  



Syntax::

  "string" "string" ...



``--owner`` (string)


  The owner of the bundles to retrieve. This parameter cannot be combined with any other filter parameter.

   

  This contains one of the following values:

   

   
  * null - Retrieves the bundles that belong to the account making the call.
   
  * ``AMAZON`` - Retrieves the bundles that are provided by AWS.
   

  

``--next-token`` (string)


  The ``NextToken`` value from a previous call to this operation. Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your WorkSpace bundles**

This example describes all of the WorkSpace bundles that are provided by AWS.

Command::

  aws workspaces describe-workspace-bundles --owner AMAZON

Output::

  {
      "Bundles": [
          {
              "ComputeType": {
                  "Name": "PERFORMANCE"
              }, 
              "Description": "Performance Bundle", 
              "BundleId": "wsb-b0s22j3d7", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "100"
              }, 
              "Name": "Performance"
          }, 
          {
              "ComputeType": {
                  "Name": "VALUE"
              }, 
              "Description": "Value Base Bundle", 
              "BundleId": "wsb-92tn3b7gx", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "10"
              }, 
              "Name": "Value"
          }, 
          {
              "ComputeType": {
                  "Name": "STANDARD"
              }, 
              "Description": "Standard Bundle", 
              "BundleId": "wsb-3t36q0xfc", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "50"
              }, 
              "Name": "Standard"
          }, 
          {
              "ComputeType": {
                  "Name": "PERFORMANCE"
              }, 
              "Description": "Performance Plus Bundle", 
              "BundleId": "wsb-1b5w6vnz6", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "100"
              }, 
              "Name": "Performance Plus"
          }, 
          {
              "ComputeType": {
                  "Name": "VALUE"
              }, 
              "Description": "Value Plus Office 2013", 
              "BundleId": "wsb-fgy4lgypc", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "10"
              }, 
              "Name": "Value Plus Office 2013"
          }, 
          {
              "ComputeType": {
                  "Name": "PERFORMANCE"
              }, 
              "Description": "Performance Plus Office 2013", 
              "BundleId": "wsb-vbsjd64y6", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "100"
              }, 
              "Name": "Performance Plus Office 2013"
          }, 
          {
              "ComputeType": {
                  "Name": "VALUE"
              }, 
              "Description": "Value Plus Bundle", 
              "BundleId": "wsb-kgjp98lt8", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "10"
              }, 
              "Name": "Value Plus"
          }, 
          {
              "ComputeType": {
                  "Name": "STANDARD"
              }, 
              "Description": "Standard Plus Office 2013", 
              "BundleId": "wsb-5h1pf1zxc", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "50"
              }, 
              "Name": "Standard Plus Office 2013"
          }, 
          {
              "ComputeType": {
                  "Name": "STANDARD"
              }, 
              "Description": "Standard Plus Bundle", 
              "BundleId": "wsb-vlsvncjjf", 
              "Owner": "Amazon", 
              "UserStorage": {
                  "Capacity": "50"
              }, 
              "Name": "Standard Plus"
          }
      ]
  }


======
Output
======

Bundles -> (list)

  

  An array of structures that contain information about the bundles.

  

  (structure)

    

    Contains information about a WorkSpace bundle.

    

    BundleId -> (string)

      

      The bundle identifier.

      

      

    Name -> (string)

      

      The name of the bundle.

      

      

    Owner -> (string)

      

      The owner of the bundle. This contains the owner's account identifier, or ``AMAZON`` if the bundle is provided by AWS.

      

      

    Description -> (string)

      

      The bundle description.

      

      

    UserStorage -> (structure)

      

      A  UserStorage object that specifies the amount of user storage that the bundle contains.

      

      Capacity -> (string)

        

        The amount of user storage for the bundle.

        

        

      

    ComputeType -> (structure)

      

      A  ComputeType object that specifies the compute type for the bundle.

      

      Name -> (string)

        

        The name of the compute type for the bundle.

        

        

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``NextToken`` parameter in a subsequent call to this operation to retrieve the next set of items. This token is valid for one day and must be used within that timeframe.

  

  

