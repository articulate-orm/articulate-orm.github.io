GENERAL

We need to mention quality goal, tests coverage, mutation testing score.

Main page:

Each EntityManager owns its own IdentityMap and UnitOfWork — no process-wide singletons, no global state. – needs rephrasing. For one entityManager there could be multiple UnitOfWorks. Singleton would still be preferable (since it's a common standard), but we have some flexibility. 

Attribute-driven metadata – maybe mention that the goal is to have it closer to code

Deliberate shared-table writes – I think it is not clear that there will be minimal required writes combined.

Next:-links blocks should all be clickable, not just a link.

Getting started:

If you’re switching between MySQL and PostgreSQL migration folders (as the demo project does), also set ARTICULATE_MIGRATIONS_PATH so migration commands know which directory to read/write. – this is not relevant to anyone, this is only a demo thing. To demonstrate.

We need to add link to symfony bundle. Like "Using Symfony? Even better ->".

Context-Bounded Entities page:

Maybe mention "slice" in a description entry part. 

"Probably not needed" – we can mention that this might be handy in a future instead of "well, then not use us at all".

Also we need to mention warm-metadata-cache command.

"Unit of Work & Identity Map" page:

We should highlight an approach to create unit-of-work for specific part of the process and clear it right away. Or store persisted between iterations entities into main unit-of-work and clear other one. One entity manager will still have those.

"$em->clear()" - should add `<nobr>` (for code in general).

"Query Builder" page:

Use whereNull() for SQL null checks. where('column', null) currently compiles as column = ? with a null parameter instead — see Known Limitations. - should be implemented, double check.

Double check `chunk` method availability, should be available.

Pagination & Filtering page:

Place cursor pagination first, in the code example we need to see what $cursor variable contains.
We need a bit more instructions about soft delete filter: how to enable it.

Lifecycle Callbacks page:

Events should be described in more details.
Set created_at or updated_at timestamps. – we have some attribute to do this automatically.

Transaction & Locking page:
An inventory-decrement flow locks stock rows before decrementing - what does this means?

Optimistic Locking page:

We need to rephrase it. No need to specify what "breaks". Instead highlight improved correctness in comparison to "one table=one entity" approach.


Performance page:

mention batch method?

Architecture page:

rename to Development or similar?