TODO
====

 * Implement indexing of resources
 * If calculations of calculations are permitted, then the current implementation
   is buggy, and calculations need to be performed in dependency-order.  If not,
   ResultDescriptor should except if you try this.  Either way, a test is needed.
 * Revisit the ValueType classes.  Is this the right way to go about it, (a blob
   that stores a binary encoded value according to the type).  Do we have the
   right set of types?
 * Add licensing
 * Have added to a CI system
 * Consider removing memory backend module
 * Consider removing camel backend module
 * Implement an alternative storage backend

newts-cassandra
---------------
 * Cassandra drivers DEBUG output is very chatty; Create a logging
   configuration for the tests, level INFO.
 * Implement temporal row-key partitioning
 * Make column TTLs an option
 * Use a prepared statement in CassandraSampleRepository#cassandraSelect
 * Enable CQL driver compression
 * Consider moving result processing code into its own module
 * Better handle schema creation, (better as-in, not a flat file containing
   CQL markup buried in src/main/resources).

newts-rest
----------
 * Implement report/result descriptor creation via REST interface
 * Add calculations to report/result descriptor representation
 * Properly handle optional resolution query argument (default to something
   reasonable)
 * Add duration query arg (use in place of start/end)
 * Clean up unused code from Transform
 * Use custom parameters for Timestamps and Duration.  It's tempting to use
   Timestamp and Duration directly, but that would mean introducing
   depenedencies on Dropwizard and Joda to newts-api (so best not to).
   *Note: Classes (TimestampParam/DurationParam) have been created, but result
   in Jersey exceptions that cause the resource(s) to not load.  This needs to
   be sussed out.*
 * Add attributes to SampleDTO

newts-gsod
----------
 * For sake of consistency, considering making import/export use the REST
   interface, instead of connecting directly to Cassandra.