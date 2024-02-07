# Introduction
## Historical Perspective
Databases are systems that serve as abstract representations of reality and model real world changes as transactions. Historically this has been done using a number of different storage media: clay tablets, papyrus, paper, punch cards, magnetic tape, hard disks, etc.

Common uses of transaction based computer systems include communications, commerce, finance, travel, manufacturing, and process control. (this list is perhaps a bit dated)

## What is a Transaction Processing System?
A transaction processing system is comprised of multiple services that support features for many different types of users. This includes automation, application programming, query execution, and administration. Clients submit queries and updates to the applicaton. The application stores data from clients in a database that serves as an abstraction of real-world state. Application responses to client queries return information from the database that is often used to determine if/when/how to make a change to the real-world state.  The many pieces of the system typically exist on a network, are geographically distributed, comprised of software and hardware from many different vendors, expected to be highly available and to respond to incoming requests within a short time window.

Within a TP system there is a core set of services called the TP monitor that shepherd transactions through the system.

___
### ACID
**Atomicity:**
All changes to the state encompassed within a single transaction are atomic. If any one change within a transaction fails then all changes within the transaction are rolled back. This includes database changes, messages, and external side-effects.

**Consistency:** Transformations to state within a transaction may not act inconsistently with the constraints of or violate the integrity of the state. This requires that the system enforce the correctness of the transaction.

**Isolation:** Transactions are serializable.  A transaction acting on a piece of data cannot begin until previous transactions acting on that same data have concluded - one at a time. (like a lock / mutex)

**Durability:** After data from a transaction has been committed it will not be lost in the event of a system failure or crash.
___

Transactions provide failure semantics that can be useful to share up the stack from system implementors to application programmers to clients.

Composing transactions provides a utilitarian and modular way to compose distributed applications.  Either all changes across different services within the system are successful or every state change is rolled back.  The automated response of commit vs. rollback provides an easy to use and reason-about mechanism for success and failure.
___
**Two-Phase Commit Protocol**
- Phase 1: all participants vote and prepare to commit
- Phase 2: all participants execute the commit
___
transaction-oriented systems can offer performance benefits by organizing many small operations into fewer larger ones.
___
### The End User's View of a Transaction Processing System
**Compensating Transaction:** a transaction whose intended purpose is to rollback the changes of a previous transaction.
___
### The Administrator/Operator's View of a TP System
**Repository/System Dictionary:** System configuration represented by a database and updated via transactions.

**Transaction Processing Performance Council (TPC) Metrics - TPC-A,B,C:** types of simulated load, the specifics of which are antiquated/obsolete.
___
### Application Designer's View of a TP System
**Remote Procedure Call (RPC):** a way for one process to invoke a program in another remote process as though the subroutine in the remote process were local. RPCs can also be transactional (**TRPCs**) endowing them with commit/rollback behavior and a two-phase-commit interface. TRPCs typically make use of Transaction Identifiers (tid).

**Flat Transaction:** a transaction that does not contain nested transactions or allow for partial rollbacks.

**Resource Managers** The system comes with an array of transactional resource managers that provide ACID operations on the objects they implement. Database systems, persistent programming languages, queue managers (spoolers), and window systems are typical resource managers.
___
### The Resource Manager's View of a TP System
___
### TP System Core Services
___
## A Transaction Processing System Feature List
___
### Application Development Features
___
### Repository Features
___
### TP Monitor Features
___
### Data Communication Features
___
### Database Features
___
### Operations Features
___
### Education and Testing Features
___
### Feature Summary
___
## Summary
___
## Historical Notes

