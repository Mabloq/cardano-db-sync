.. raw:: html

   <p align="center">
   </p>


****************************
``cardano-db-sync`` Overview
****************************

The cardano-db-sync component consists of a set of components:

-  ``cardano-db`` which defines common data types and functions used by
   any application that needs to interact with the data base from
   Haskell. In particular, it defines the database schema.
-  ``cardano-db-sync`` which acts as a Cardano node, following the chain
   and inserting data from the chain into a PostgreSQL database.
-  ``cardano-db-sync-extended`` is a relatively simple extension to
   ``cardano-db-sync`` which maintains an extra table containing epoch
   data.

The two versions ``cardano-db-sync`` and ``cardano-db-sync-extended``
are fully compatible and use identical database schema. The only
difference is that the extended version maintains an ``Epoch`` table.
The non-extended version will still create this table but will not
maintain it.