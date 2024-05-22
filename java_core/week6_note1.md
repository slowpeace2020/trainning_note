## JDBC
steps: connection -> statement -> sql query -> process sql -> close connection/statement
select, update, insert(whole,partial),delete;
Atomic transaction, (commit, rollback)
batchprocessing
PreparedStatement -> SQL injection
Statement vs PrepearedStatement vs CallableStatement

## Hibernate
ORM object relational mapping

tool: Hibernate, MyBatis
JPA: java persistence API, specification

### Hibernate Architecture

### Entity LifeCycle
1. Transient
2. Persistent
3. Detached
4. Removed

### Mapping
OneToOne
OneToMany
ManyToOne
ManyToMany

### Cascade type
persist
Merge(update database with new entity)
Refresh(opposite with merge)
Remove
Detach
All


Hibernate Fetch types

### Fetch type
lazy loading
eager loading

OneToOne: eager
ManyToOne: eager
OneToMany: lazy
ManyToMany: lazy

### First level Cache/ Second level cache






