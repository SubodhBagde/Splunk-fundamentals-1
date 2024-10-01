# Describe Lookups:

- Lookups enrich your event data by adding field-value combinations from lookup tables.

- Splunk software uses lookups to match field-value combinations in your event data with field-value combinations in external lookup tables.

- If Splunk software find those field-value combinations in your lookup table, Splunk software will append the corresponding field value combinations in the table to the events in  your search.

- Types of Lookups:

  * CSV Lookups
 
  * External Lookups
 
  * KV Store Lookups
 
  * Geospatial Lookups
 
- Use the lookup command to invoke field value lookups.

  **Syntax**: lookup lookup-table-name lookup-field1 AS event-field1,lookup-field2 AS event-field2 OUTPUTNEW lookup-destfield1 AS event-destfield1

# Lookup table files:

- Lookup table files are files that contain a lookup table. A standard lookup pulls field out of this table and add them to your events when corresponding fields in the table are matched in your events.

- All lookup types uses lookup tables, but only 2 lookup types require that you upload a lookup table file: CSV lookups and Geospatial lookups. A single lookup table file can be used by multiple lookup definitions.

# Configure Lookup table files:

![image](https://github.com/SubodhBagde/Splunk-fundamentals-1/assets/136182792/11ac4942-0180-43dc-88ef-f3c46ab9cfc5)

# Lookup definition:

- A lookup definition provides a lookup name and a path to find the lookup table.

- Lookup definition can include extra setting such as matching rules, or restriction on the fields that the lookup is allowed to match. One lookup table can have multiple lookup definition.

# Configure Lookup definition:

![image](https://github.com/SubodhBagde/Splunk-fundamentals-1/assets/136182792/15e74ee5-8a78-4520-9e63-29e41b19d43c)

# Automatic Lookup:

- Use automatic lookups to apply a lookup to all searches at search time. After you define an automatic lookup for a lookup definition, you do not need to manually invoke it in searches with lookup command.

# Configure Automatic Lookup:

![image](https://github.com/SubodhBagde/Splunk-fundamentals-1/assets/136182792/b8a9b3d9-5b4e-4793-9fd4-c0838a57afe4)

![image](https://github.com/SubodhBagde/Splunk-fundamentals-1/assets/136182792/d37e5e7d-6fb8-461a-9653-2784b6850a79)

