Testing
=======

Scope
-----


* Test Request/Response
     Defined in the postman/collection.
     Collected as pytest collection in test folder.
* Test Scripts
     Test fhir dependency (Patient exists in test repository, resources exist)
     Test retreival from script program.
     Test Mapping of resources
* Error handling
     404-type errors
     Network issues
     Authentication issues(future work)
     Mapping handling issues
* Reporting issue endpoint
     If CQL error, add an endpoint to handle the collection of errors.
* Persistence Testing
     Need to persist existing of Job/Task between restarts