###### **Conceptual Model:** 
- We use lines to connect the 2 entities, so we do not need to add foreign keys. Since the relationship is established from the connection

**Example of Conceptual model**

![[Pasted image 20250830173428.png]]

*This is not allowed in the conceptual model*
![[Pasted image 20250805165059.png]]
###### **Cardinality**
![[Pasted image 20250805171019.png]]

###### Non-Identifying Relationship**
![[Pasted image 20250805171852.png]]

If any of the tables do not have any of each other's keys, then we have to mark them as *non-identifying.* Marked as a dotted line. 

###### **Identifying Relationship**

![[Pasted image 20250830190533.png]]
A relationship where a **weak entity** depends on a **strong (owner) entity** for its identification

**Strong Entity**
Has a key which may be defined without reference to other entities
The parent’s PK may appear as a **foreign key** in the child, but it is not part of the child’s primary key

**Weak Entity**
Has a key which requires the existence of one or more other entities. 
The weak entity’s primary key includes the owner entity’s primary key.

**Multi-Valued**
An attribute that can have **more than one value** for a single entity.
A `Person` can have multiple `PhoneNumbers`.

**Composite**
An attribute that can be **broken down into smaller sub-attributes** with their own meaning.
`FullName` → can be divided into `FirstName`, `MiddleName`

###### **Relation Properties**

- Tuples must be unique 
- Tuples are unordered within a relation
- No ordering of attributes within a tuple
- Tuple values are atomic

**Relation Heading (Schema)**

`CUSTOMER(custno, custname, custadd, custcredlimit)`

**Relation Body (Instance/State)**

`r(R) = {t1, t2, …, tm}`
- **Degree** = number of attributes (columns).
- **Cardinality** = number of tuples (rows).

**Superkey**
- A **superkey** is a **set of one or more attributes** that can **uniquely identify a tuple (row)** in a relation
- So, any set of attributes that ensures **no two rows are identical** is a superkey.

**Candidate Key**
- A **minimal superkey** → no attribute can be removed without losing uniqueness.
- Basically a candidate for a primary key

**Primary Key**
- One candidate key chosen by the designer as the **main identifier**.

##### Data Integrity

**Entity integrity**
- Primary key value must not be NULL

**Referential integrity**
- The values of FK must either match a value of a full PK in the related relation or be NULL

**Column/Domain integrity**
- All values in a given column must come from the same domain (same type and valid values)

##### Relational Algebra 

**Selection (σ)**
- Picks **rows** from a relation that satisfy a condition.
- Symbol: `σ condition (Relation)`
- Example: Get students older than 20:

####### **Projection (π)**
- Picks **columns** from a relation.
- Symbol: `π attribute_list (Relation)`
- Example: Get only names and emails of students:

####### **Union (⋃)
- Combines tuples from two relations (duplicates removed).
- Both relations must have the same schema.
- Example: Students from two campuses:

####### **Set Difference (−)**
- Tuples in one relation but not in the other.
- Example: Students who enrolled last year but not this year

####### **Cartesian Product (×)**
- Pairs every tuple of one relation with every tuple of another.
- Basis for **joins**.

####### **Join (⨝)**
- Combines tuples from two relations based on a condition.
- Example: Get students with their enrolled courses:

####### **Intersection (⋂)**
- Tuples common to both relations.
- Example: Students enrolled in both Math and Science.

####### **Division (÷)**
- Finds tuples in one relation that are related to **all tuples** in another relation.
- Example: Find students who have taken **all courses** offered.

####### Normalization

Normalization is the process of organizing data in a database to:

1. Remove **redundancy** (duplicate data).
2. Avoid **update anomalies** (problems when inserting, deleting, or updating data).
3. Ensure **data integrity** (consistency

*Anomalies*
- **INSERT Anomaly** – When adding data to a relation you are required to add other (related) data  Danger: other data may not be available so cannot proceed with the insert  

- **UPDATE Anomaly** – Changing a value for an attribute requires multiple tuples to be changed – Danger: only some tuples will be updated leading to inconsistent data 

- **DELETE Anomaly** – When a tuple in a relation is deleted, all tuple data is removed – Danger: related data, which may be the only such data will be lost

###### **Types of Functional Dependency**

###### Total (or Mutual) Dependency

- Two attributes uniquely determine each other.
   `emp_no ➔ emp_taxfileno`
   `emp_taxfileno ➔ emp_no`
- Either one can act as the key for the other
  
**Full vs Partial Dependency**

- **Full Dependency**:
    - A non-key attribute depends on the _whole_ composite key.
    - `(order_no, prod_no) ➔ ol_qtyordered`
        
- **Partial Dependency**:
    - A non-key attribute depends on _part_ of the composite key, not the full key.
    - `(order_no, prod_no) ➔ prod_desc`
        - But really, just `prod_no ➔ prod_desc`.
        - 
**Transitive Dependency**
- A non-key attribute depends on another non-key attribute, which depends on the key.
    - `order_no ➔ cust_no`
    - `cust_no ➔ cust_name`
    - So indirectly: `order_no ➔ cust_name`.

##### SQL Referential Integrity
- RESTRICT 
	Deletion of tuples is NOT ALLOWED for those tuples in the table referred by the FK (the table containing PK) if there is corresponding tuple in the table containing the FK. 

- CASCADE 
	A deletion of a tuple in the table referred by the FK (the table containing PK) will result in the deletion of the corresponding tuples in the table containing the FK. 

- NULLIFY 
	A deletion of a tuple in the table referred by the FK (the table containing PK) will result in the update of the corresponding tuples in the table containing the FK to NULL.

