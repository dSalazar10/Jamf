SYNOPSIS:
=========
There are four main systems of record for Endpoint Management: Jamf, Microsoft System Center Configuration Manager, BigFix, and ServiceNow.  In some way, each of these systems provides a programmatic interface with which to extract and/or provide metrics.

The goal of the project is to compare and contrast the four system’s capabilities and provide useful analytics on endpoint management, in the process. The initial phase will focus on patching. The plan is to use Python for data collection and R for data analysis. 

The HTTP library of choice for Python will be ‘requests’, which will be used to perform HTTP/1.1 requests to the four REST APIs. This will provide us will three JSON data sets (Jamf, MSCCM, and ServiceNow) and one XML dataset (BigFix). 
The JSON library of choice will be ‘json’, which will be used to parse the JSON datasets. 
The XML library of choice will be ‘xmltodict’, which will be used to parse the XML dataset.
As it turns out, ‘requests’ has the ability to convert from XML to JSON with a function call.

Once the datasets are extracted and parsed, the data is assembled into ‘panels’ and returned as ‘Pandas’ DataFrames, which can be manipulated and displayed with Python or R.

PROGRAMMATIC INTERFACES:
=========================
Jamf: JSS REST API
https://bryson3gps.wordpress.com/2014/03/30/the-jss-rest-api-for-everyone/

MSCCM: System Center Orchestrator OData REST API
https://blogs.technet.microsoft.com/orchestrator/2012/03/18/accessing-system-center-2012-orchestrator-using-the-web-service/

BigFix: BigFix REST API
https://developer.bigfix.com/rest-api/

ServiceNow: Scripted REST API
https://docs.servicenow.com/bundle/kingston-application-development/page/integrate/custom-web-services/reference/r_ScriptedRESTServiceScriptExamples.html

POSSIBLE METRICS TO EXTRACT/DISPLAY:
====================================
Number of critical patches available/delivered per-unit-time, per endpoint
Number of critical patches delivered by type-of-os
Number of patches available but undelivered per endpoint
Number of patches available per endpoint by level-of-risk categorization
History of patches delivered over time by geographic group


OTHER REFERENCES:
==================

request Library Docs: 
http://docs.python-requests.org/en/master/

Example of JSSAPI with python: https://github.com/sreyemnayr/jamf_pro_api/blob/master/jssapi/jssapi.py

XML to JSON:
http://tripsintech.com/xml-to-json-python-script-also-json-to-xml/

Parsing JSS JSON:
https://apple.lib.utah.edu/fetching-data-from-the-jss-using-api-calls-python/

SNOW REST API:
https://developer.servicenow.com/app.do#!/rest_api_doc?v=jakarta&id=r_SCatAPIListOfCatalogsGET

BigFix Examples:
https://github.com/bigfix

Training:
http://support.bigfix.com/fixlet/documents/CustomAuthoringTrainingGuide-6-17-2005.pdf

Download Fixlet Debugger:
https://www.google.com/url?q=https://www.ibm.com/developerworks/community/wikis/home?lang%3Den%23!/wiki/Tivoli%2520Endpoint%2520Manager/page/Fixlet%2520Debugger%2520%28QnA%29%2520Tool/comment/da475ee7-e0a7-408a-a257-072404b4a1bd&sa=D&source=hangouts&ust=1531876493333000&usg=AFQjCNHiKZAwpXaOG48WdnT-YnjCa8hbUg

Examples of Data analysis in both R and Python:
https://www.dataquest.io/blog/python-vs-r/

EXAMPLES:

R and Python Analytics via Jupyter, Reticulate, and BigFIx:


