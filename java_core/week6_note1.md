### JDBC

**Steps:**

1. **Connection**: Establish a connection to the database using JDBC DriverManager and provide necessary connection parameters such as URL, username, and password.

2. **Statement**: Create a Statement object to execute SQL queries on the database. There are three types of statements: Statement, PreparedStatement, and CallableStatement.

3. **SQL Query**: Construct and execute SQL queries (e.g., SELECT, UPDATE, INSERT, DELETE) using the Statement object.

4. **Process SQL**: Process the SQL query result set returned by the database, if applicable. Iterate through the ResultSet object to retrieve query results.

5. **Close Connection/Statement**: Close the connection and statement objects to release database resources and prevent memory leaks.

**SQL Operations:**

- **Select**: Execute a SELECT query to retrieve data from the database.
- **Update**: Execute an UPDATE query to modify existing data in the database.
- **Insert**: Execute an INSERT query to add new data to the database.
    - Whole: Insert entire record into the table.
    - Partial: Insert specific columns into the table.
- **Delete**: Execute a DELETE query to remove data from the database.

**Atomic Transaction:**

- JDBC supports atomic transactions, ensuring that a series of database operations are treated as a single unit of work.
- Use the `commit` method to permanently save the changes made during the transaction, or the `rollback` method to discard them.

**Batch Processing:**

- JDBC supports batch processing for executing multiple SQL statements as a batch to improve performance and reduce network overhead.

**PreparedStatement:**

- PreparedStatement is a precompiled SQL statement that can be executed multiple times with different parameters.
- Helps prevent SQL injection attacks by automatically escaping special characters in parameter values.

**Statement vs PreparedStatement vs CallableStatement:**

- **Statement**: Used for executing static SQL queries without parameters.
- **PreparedStatement**: Used for executing parameterized SQL queries to prevent SQL injection attacks.
- **CallableStatement**: Used for executing stored procedures with input and output parameters.

### Hibernate

**ORM (Object Relational Mapping):**

- Hibernate is an ORM framework that maps Java objects to database tables and simplifies database interaction in Java applications.

**Tools:**

- Hibernate and MyBatis are popular ORM frameworks for Java applications.
- JPA (Java Persistence API) is a specification for managing relational data in Java applications.

### Hibernate Architecture

- **Session Factory**: Factory for creating Hibernate Session objects.
- **Session**: Main interface for database interactions in Hibernate.
- **Configuration**: Configuration settings for Hibernate such as database connection properties and mapping files.
- **Mapping Files (hbm.xml)**: XML files that define the mapping between Java objects and database tables.

### Entity Lifecycle

1. **Transient**: Object is not associated with any Hibernate Session and has no persistent representation in the database.
2. **Persistent**: Object is associated with a Hibernate Session and has a persistent representation in the database.
3. **Detached**: Object was once associated with a Hibernate Session but is no longer. It still has a persistent representation in the database.
4. **Removed**: Object was associated with a Hibernate Session but has been deleted from the database.

### Mapping

- **OneToOne**: Represents a one-to-one association between two entities.
- **OneToMany**: Represents a one-to-many association between two entities.
- **ManyToOne**: Represents a many-to-one association between two entities.
- **ManyToMany**: Represents a many-to-many association between two entities.

### Cascade Type

- **Persist**: Automatically persists associated entities when the owning entity is persisted.
- **Merge**: Updates the database with changes made to detached entities when the owning entity is merged.
- **Refresh**: Reloads the state of associated entities from the database when the owning entity is refreshed.
- **Remove**: Removes associated entities when the owning entity is removed.
- **Detach**: Detaches associated entities from the Hibernate Session.

### Hibernate Fetch Types

- **Lazy Loading**: Associations are loaded only when accessed for the first time.
- **Eager Loading**: Associations are loaded immediately when the owning entity is loaded.

**Fetch Types for Various Associations:**

- **OneToOne**: Eager Loading.
- **ManyToOne**: Eager Loading.
- **OneToMany**: Lazy Loading.
- **ManyToMany**: Lazy Loading.

### First Level Cache/ Second Level Cache

- **First Level Cache**: Session-level cache that stores objects retrieved from the database during a Hibernate Session.
- **Second Level Cache**: Application-wide cache that stores objects retrieved from the database across multiple Hibernate Sessions. Helps improve performance by reducing database queries.