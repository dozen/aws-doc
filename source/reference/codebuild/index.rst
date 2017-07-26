[ :ref:`aws <cli:aws>` ]

.. _cli:aws codebuild:


*********
codebuild
*********



===========
Description
===========

 

AWS CodeBuild is a fully managed build service in the cloud. AWS CodeBuild compiles your source code, runs unit tests, and produces artifacts that are ready to deploy. AWS CodeBuild eliminates the need to provision, manage, and scale your own build servers. It provides prepackaged build environments for the most popular programming languages and build tools, such as Apach Maven, Gradle, and more. You can also fully customize build environments in AWS CodeBuild to use your own build tools. AWS CodeBuild scales automatically to meet peak build requests, and you pay only for the build time you consume. For more information about AWS CodeBuild, see the *AWS CodeBuild User Guide* .

 

AWS CodeBuild supports these operations:

 

 
* ``batch-get-projects`` : Gets information about one or more build projects. A *build project* defines how AWS CodeBuild will run a build. This includes information such as where to get the source code to build, the build environment to use, the build commands to run, and where to store the build output. A *build environment* represents a combination of operating system, programming language runtime, and tools that AWS CodeBuild will use to run a build. Also, you can add tags to build projects to help manage your resources and costs. 
 
* ``create-project`` : Creates a build project. 
 
* ``delete-project`` : Deletes a build project. 
 
* ``list-projects`` : Gets a list of build project names, with each build project name representing a single build project. 
 
* ``update-project`` : Changes the settings of an existing build project. 
 
* ``batch-get-builds`` : Gets information about one or more builds. 
 
* ``list-builds`` : Gets a list of build IDs, with each build ID representing a single build. 
 
* ``list-builds-for-project`` : Gets a list of build IDs for the specified build project, with each build ID representing a single build. 
 
* ``start-build`` : Starts running a build. 
 
* ``stop-build`` : Attempts to stop running a build. 
 
* ``list-curated-environment-images`` : Gets information about Docker images that are managed by AWS CodeBuild. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  batch-get-builds
  batch-get-projects
  create-project
  delete-project
  list-builds
  list-builds-for-project
  list-curated-environment-images
  list-projects
  start-build
  stop-build
  update-project
