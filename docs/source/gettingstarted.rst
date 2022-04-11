Getting Started
===============




Terminology
-----------
As this project covers a diverse array of disciplines, this page defines application related terminology to distinguish explicit usage of terms/phrases between the RC-API workflow, FHIR, and broader Software Development.

CQL (Clinical Quality Language) - CQL is a high-level language designed for representing clinical logic in analysis of FHIR resources, such as for decision support. For more information, please visit: `https://cql.hl7.org/`.
CQL Library - A CQL Library is a discrete set of CQL instructions that are ran together, with each instruction being considered a "task", stored as a FHIR Library resource. "Library" captures both the semantic concept of a collection of CQL queries and the FHIR Library resource data structure itself. A library is a persistent, static entity which may be executed, with a single execution of a library being a "job".
Form (See also: Job Package) - A form is an alternative name for a "job package", more specifically related to a job package's representation as a development artifact which is typically a user friendly spreadsheet stored in CSV format. It may be thought of as the build file for a job package. There may also be overlap with the usage of the concept of a "form" in a broader context, such as the UI rendering of a series of questions and answers documented in a job package as an HTML form. (The term "job package" should be preferred for all discussion related to run time execution.)
Job - A job is an action that is the execution of a library. It is a dynamic entity that exists in a moment and is not persisted beyond its own lifecycle.
Task - A "task" is a single discrete piece of a job, such as a specific CQL statement in a CQL library.
Questionnaire (FHIR) - A Questionnaire is a FHIR resource which is the standardized data structure used to represent a job package. Typically a "form" is created in a spreadsheet, converted/exported to a CSV, and then converted to a Questionnaire resource.