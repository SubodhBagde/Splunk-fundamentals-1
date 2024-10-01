# Four stages of Splunk includes:

1. Accepts any text data as input
2. Parses the data into events
3. Stores events in indexes
4. Searches and reports


# There are 3 primary components of Splunk architecture:
1. Forwarder - The forwarder is an agent you deploy on IT systems, which collects logs and sends them to the indexer.
   Splunk has two types of forwarders:

   a) Universal Forwarder – forwards the raw data without any prior treatment. This is faster, and requires less resources on the host, but results in huge quantities of data sent to the indexer.
   
   b) Heavy Forwarder – performs parsing and indexing at the source, on the host machine and sends only the parsed events to the indexer.

2. Indexer - The indexer transforms data into events (unless it was received pre-processed from a heavy forwarder), stores it to disk and adds it to an index, enabling searchability.

   The indexer creates the following files, separating them into directories called buckets:

   * Compressed raw data
  
   * Indexes pointing to raw data (.TSIDX files)
  
   * Metadata files
  
   The indexer performs generic event processing on log data, such as applying timestamp and adding source, and can also execute user-defined transformation actions to extract specific information or apply special rules, such as filtering unwanted events.
   
3. Search Head - The search head provides the UI users can use to interact with Splunk. It allows users to search and query Splunk data, and interfaces with indexers to gain access to the specific data they request.

   Splunk provides a distributed search architecture, which allows you to scale up to handle large data volumes, and better handle access control and geo-dispersed data. In a distributed search scenario, the search head sends search requests to a group of indexers, also called search peers.

   The indexers perform the search locally and return results to the search head, which merges the results and returns them to the user.
