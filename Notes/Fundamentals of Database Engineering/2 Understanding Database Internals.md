#### Storage Concepts
- Table
- [[#Row_ID]]
- [[#Page]]
- [[#IO]]
- [[#Heap Data Structure]]
- [[#Index Data Structure]]

##### Row_ID
- Internal and system maintained
- In MySQL, primary key is the row id
- In postgres, a new column called row-id is created.

##### Page
- Rows are stored in logical pages stored on disk.
- Database reads a page or more in single IO and from that it selects the needed rows.
- Each page has fixed size - 8KB in postgres, 16KB in MySQL.

##### IO
- IO operation is a read request to the disk
- Minimum - good.
- Each IO can fetch a page. 

##### Heap Data Structure
- Collection of pages.
- Table is stored in the heap
- Traversing the heap is expensive.
- Indexes tell exactly where the data is present in the heap.

##### Index Data Structure
- Data structure which points to the heap
- Refer to [[3 Storage and Retrieval]] for more info on indexing and how its done.
- Index tells exactly in which page the data is present.
- Index is also stored as pages in disk.
- Each index for a primary key (ex) has pointer to the page in which the row is present in the heap.


![[indexing.png]]

- In postgres, all secondary indexes point to the row_id.

#### Row vs Column Oriented Databases

##### Row-Oriented Database
- Tables are stored as rows in disk
- A single block io reads a single page which contains multiple rows.
- Once we find a row, we get all the columns

##### Column-Oriented Database
- Tables are stored as columns first in disk.
- Each page will contain only a specific column
- A single IO read to the table fetches multiple columns / pages with all matching rows
- Mainly used for [[3 Storage and Retrieval#Transaction Processing or Analytics|OLAP]] where aggregate functions are used mainly.
- Each column's value for a row will be tagged along with its primary key. Ex: (firstname,id) , (lastname,id) where firstname and lastname are secondary columns and id is primary key. 
- [[3 Storage and Retrieval#Aggregation Data Cubes and Materialized Views|Aggregations]]

#### Primary vs Secondary Index
##### Primary Index
- Heap itself is __organized__ around that index
- Called as _clustering index_. Refer [[3 Storage and Retrieval#Secondary Index|clustered index]].  

##### Secondary Index
- Not organized around anything.
- Basically secondary indexes will point to row_id (in postgres). So upon reading a row, first we need to find row_id and then find the row using the row_id from the disk's pages.
