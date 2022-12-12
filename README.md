![enter image description here](wires.png)
# SCANOSS Agent for FOSSology 
### Background
This is a temporary repository only useful until the SCANOSS Agent contribution is merged into FOSSology.
Active Pull request can be found [here](https://github.com/fossology/fossology/pull/2167) 


<h3>Introduction</h3>


This document describes the steps followed to deploy the FOOSology toolkit version that includes a SCANOSS Agent tool. The SCANOSS Agent provides with: 



* License detection
* PURL identification
* Snippet Matching feature
* Source and path location of the original code

At the time of writing this document, SCANOSS Agent source code is waiting to be merged to FOSSology main branch so instructions to deploy from an alternative repository fork are provided.

<h3>Instructions</h3>


1 - Clone the alternative fork from [https://github.com/scanoss-qg/fossology](https://github.com/scanoss-qg/fossology)

2 - Move to the SCANOSS Branch using: 

        # git checkout scanoss-qg/2166/scanoss-agent

3 - Follow instructions for installing FOSSology from source ([here](https://github.com/fossology/fossology/wiki/Install-from-Source))



1. Install dependencies: 

        # utils/fo-installdeps

2. Build FOSSology:

        $ make

3. Install FOSSology:

        # make install

4. Run the postinstall script:

        # /usr/local/lib/fossology/fo-postinstall


<h3>Usage</h3>




* From Fossology main menu, select **_upload a file_**. FOSSology accepts and unzip compressed files automatically
* From the list of tools, Check **_SCANOSS Toolkit option_**
* Wait for the scan to be finished

This agent calculates fingerprints from the source code analyzed and submits them to the OSSKB.org API to compare with the database of known Open Source. Only fingerprints are sent, so your code keeps CONFIDENTIAL.

Results from license information are stored on FOOSology DB tables. However, the agent places information about snippets or file matching on its own tables.

To view File information from a scanned file, just click on the **_info_** tab. You will be presented with:



* Type of match (full file or snippet)
* Line ranges
* Matching file and path inside the repository
* PURL
* URL
