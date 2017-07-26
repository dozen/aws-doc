[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-application-revisions:


**************************
list-application-revisions
**************************



===========
Description
===========



Lists information about revisions for an application.



========
Synopsis
========

::

    list-application-revisions
  --application-name <value>
  [--sort-by <value>]
  [--sort-order <value>]
  [--s-3-bucket <value>]
  [--s-3-key-prefix <value>]
  [--deployed <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--sort-by`` (string)


  The column name to sort the list results by:

   

   
  * registerTime: Sort the list results by when the revisions were registered with AWS CodeDeploy.
   
  * firstUsedTime: Sort the list results by when the revisions were first used by in a deployment.
   
  * lastUsedTime: Sort the list results by when the revisions were last used in a deployment.
   

   

  If not specified or set to null, the results will be returned in an arbitrary order.

  

  Possible values:

  
  *   ``registerTime``

  
  *   ``firstUsedTime``

  
  *   ``lastUsedTime``

  

  

``--sort-order`` (string)


  The order to sort the list results by:

   

   
  * ascending: Sort the list of results in ascending order.
   
  * descending: Sort the list of results in descending order.
   

   

  If not specified, the results will be sorted in ascending order.

   

  If set to null, the results will be sorted in an arbitrary order.

  

  Possible values:

  
  *   ``ascending``

  
  *   ``descending``

  

  

``--s-3-bucket`` (string)


  A specific Amazon S3 bucket name to limit the search for revisions.

   

  If set to null, then all of the user's buckets will be searched.

  

``--s-3-key-prefix`` (string)


  A specific key prefix for the set of Amazon S3 objects to limit the search for revisions.

  

``--deployed`` (string)


  Whether to list revisions based on whether the revision is the target revision of an deployment group:

   

   
  * include: List revisions that are target revisions of a deployment group.
   
  * exclude: Do not list revisions that are target revisions of a deployment group.
   
  * ignore: List all revisions, regardless of whether they are target revisions of a deployment group.
   

  

  Possible values:

  
  *   ``include``

  
  *   ``exclude``

  
  *   ``ignore``

  

  

``--next-token`` (string)


  An identifier that was returned from the previous list application revisions call, which can be used to return the next set of applications in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about application revisions**

This example displays information about all application revisions that are associated with the specified application.

Command::

  aws deploy list-application-revisions --application-name WordPress_App --s-3-bucket CodeDeployDemoBucket --deployed exclude --s-3-key-prefix WordPress_ --sort-by lastUsedTime --sort-order descending

Output::

  {
      "revisions": [
          {
              "revisionType": "S3",
			  "s3Location": {
                "version": "uTecLusvCB_JqHFXtfUcyfV8bEXAMPLE",
                "bucket": "CodeDeployDemoBucket",
                "key": "WordPress_App.zip",
				"bundleType": "zip"
		      }
          },
          {
              "revisionType": "S3",
			  "s3Location": {
                "version": "tMk.UxgDpMEVb7V187ZM6wVAWEXAMPLE",
                "bucket": "CodeDeployDemoBucket",
                "key": "WordPress_App_2-0.zip",
				"bundleType": "zip"
	          }
          }
      ]
  }


======
Output
======

revisions -> (list)

  

  A list of revision locations that contain the matching revisions.

  

  (structure)

    

    Information about an application revision's location.

    

    revisionType -> (string)

      

      The application revision's type:

       

       
      * S3: An application revision stored in Amazon S3.
       
      * GitHub: An application revision stored in GitHub.
       

      

      

    s3Location -> (structure)

      

      Information about the location of application artifacts that are stored in Amazon S3.

      

      bucket -> (string)

        

        The name of the Amazon S3 bucket where the application revision is stored.

        

        

      key -> (string)

        

        The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

        

        

      bundleType -> (string)

        

        The file type of the application revision. Must be one of the following:

         

         
        * tar: A tar archive file.
         
        * tgz: A compressed tar archive file.
         
        * zip: A zip archive file.
         

        

        

      version -> (string)

        

        A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

         

        If the version is not specified, the system will use the most recent version by default.

        

        

      eTag -> (string)

        

        The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

         

        If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

        

        

      

    gitHubLocation -> (structure)

      

      Information about the location of application artifacts that are stored in GitHub.

      

      repository -> (string)

        

        The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

         

        Specified as account/repository.

        

        

      commitId -> (string)

        

        The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

        

        

      

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list application revisions call to return the next set of application revisions in the list.

  

  

