# ADBISProjectHashAndSortMerge
ADBIS Project to study time complexities for Hash and Sort-merge join operations
# Join Algorithms
Implemented Join algorithms are used on Waterloo SPARQL Diversity Test Suite (WatDiv) dataset. Dateset is being vertical partitioned into tables, that are joined to the specific SPARQL query. We Implement the following Join Algorithms in this project:

- Hash Join
- Sort-Merge Join
- Partitioned Parallel Hash Join

# SPARQL Queries
An example of a SPARQL query on a different dataset:

```
(?a)---follows--->(?b)---friendOf--->(?c)---likes--->(?d)---hasReview--->(?e)
```

In this query, (?a), (?b), (?c),(?d),and (?e) are variables, and hasAuthor and hasTitle are properties. 

The corresponding SQL expression for this query would be:

```sql
SELECT follows.subject, follows.object, friendOf.object, likes.object, hasReview.object
  FROM follows, friendOf, likes, hasReview
  WHERE follows.object = friendOf.subject
        AND friendOf.object = likes.subject
        AND likes.object = hasReview.subject
```

The query in the form of relational algebra would be:

```
follows join friendOf on follows.object = friendOf.subject
friendOf join likes on friendOf.object = likes.subject
likes join hasReview on likes.object = hasReview.subject
```

By representing the SPARQL query in SQL and relational algebra, we can perform the same traversal and retrieve the mapped values of all the variables (?a), (?b), (?c), (?d), and (?e) by executing the SQL query or applying the relational algebra operations on the corresponding database or dataset.
