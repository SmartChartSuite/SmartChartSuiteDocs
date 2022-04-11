RC-API Client Development Guide
===============================

FHIR Output Bundle
------------------

#### Structure and non structure data in the valueString
While the FHIR observation value is capable of handling multiple data types, we are collapsing structure data into the single value string in order to provide a simple and fast access to the registry case data. If the value (i.e. Observation.valueString) has a structure, it's structured in the following formats with a "^" delimiter. And there are only three possible formats. Each number in { } indicates the meaning of value.

```
Format 1: {1}^{2}^{3}
Format 2: {0}^{1}^{2}^{3}
Format 3: {0}^{1}^{2}^{3}^{4}^{5}
{0}: date-time (in ISO Date format)
{1}: system
{2}: code
{3}: display
{4}: additional value
{5}: unit if {4} is numeric.
```

All {#} are optional. If any of them needs to be empty or null, it should have no data but place needs to be intact. For example, if {1} is not available for the coded value (format 1), it should be "^{2}^{3}".

Format Details:<br>
Format 1: Codeable value in system/code/display. <br>
Format 2: Codeable value with data-time. The data-time should be in ISO Date format (yyyy-MM-ddTHH:MM:SS)<br>
Format 3: Codeable value with data-time and additional value. If the additional value is string, then {5} is not required. If {4} is numeric, then {5} should be unit.

Observation.valueString with non-structure data does not need to follow these format as it's free-text.