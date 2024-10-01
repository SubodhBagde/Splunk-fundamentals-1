# Search Commands - table, rename, fields and dedup

1. **Table** - The table command returns a table that is formed by only the fields that you specify in the arguments. Columns are displayed in the same order that the fields are specified. Column headers are the field names.  Rows are the field values. Each row represents an event.

    **Syntax**: table wc-field-list

    **Example**: index = “_internal” | table _time sourcetype

2. **Rename** - Rename command is used to rename one or more fields. This command is useful for giving more fields more meaningful names. If you want to rename fields with similar names, you can use wildcard character.

    **Syntax**: rename wc-field-list AS wc-field-list…

    **Example**: rename date_hour AS hours

3. **Fields** - Keep or remove fields from search results based on the field list criteria. By default, the internal fields _raw and time are included in the output in Splunk Web. Additional internal fields are included in the output with the output csv command.

    **Syntax**: fields [+ or - ] wc-field-list

4. **Dedup** - Removes the events that contain an identical combination of values for the fields that you specify. With the dedup command you can specify the number of duplicate events to keep for each value of a single field, or for each combination of values among several fields.

    **Syntax**: dedup field-list

# Transform Commands - sort, top, rare and stats

1. **Sorts** - The sort command sorts all of the results by the specified fields. Results missing a given field that are treated as having the smallest or largest possible value of that field if the order is descending or ascending respectively. If the first argument to the sort command is a number, then at most that many result are returned in order. If the number 0 is specified, all of the results are returned.

   **Syntax**: sort count sort-by-clause… desc

2. **Top** - Finds the most common values for the fields in the field list. Calculate a count and a percentage of the frequency the values occur  in the events. If the <by-clause> is included, the results are grouped by the field you specify in the <by-clause>.

   **Syntax**: top N top-options… field-list by-clause

3. **Rare** -  Displays the least common values of a field. Finds the least frequent tuple of values of all the fields in the field list.

   **Syntax**: rare top-options… field-list by-clause

4. **Stats** - Calculate the aggregate statistics, such as average, count and sum over the results set. This is similar to SQL aggregation. If the stats command is used without a by-clause, only one row is returned, which is the aggregation over the entire incoming result set. If a by-clause is used, one row is returned for each distinct value specified in the by-clause.

   **Syntax**: stats stats-function(field) AS field… BY field
