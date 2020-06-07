## Day 12 of #dailycoding challenge ⬇️

There are three essential functions for manipulating sets: setdiff(), union(), union_all(), intersect().
We will learn :

▪ setdiff():takes the rows that appear in one vector but not in the other vector.
   ▪Note: The difference between two sets is order-dependent. It is the material that is in the first named set,
    that is not in the second named set. Thus setdiff(A,B) gives a different answer than setdiff(B,A).

▪ union(): combines all rows from both the vectors and removes duplicate records from the combined dataset.
  So the resultant vector will not have any duplicates.

▪ union_all(): combines all rows from both the vectors without removing the duplicate records from the combined dataset.

▪ intersect(): takes the rows that appear in both vectors.

▪ setequal(): tests whether two data sets
contain the exact same rows (in any order).

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !


``` r
 homo_sapiens= paste("chr", c(1:22, "X", "Y"), sep="") 
 homo_sapiens
 mus_musculus= paste("chr", c(1:19, "X", "Y"), sep="") 
 mus_musculus
 
 # Base R
 # The union of two sets is everything in the two sets taken together, but counting elements only once that are common to both sets
 union(homo_sapiens,mus_musculus)
 
 # The intersection of two sets is the material that they have in common
 intersect(homo_sapiens,mus_musculus)
 
 # check the difference between two sets 
 setdiff(homo_sapiens,mus_musculus)
 setdiff(mus_musculus,homo_sapiens)
 
 # For testing if two sets are equal
 setequal(setdiff(homo_sapiens,mus_musculus),setdiff(mus_musculus,homo_sapiens))
 
 # Dplyr has the same functions as base R which work the same 
 library(dplyr)
 set1= paste("gene", c(1:20), sep="") 
 set1
 set2= paste("gene", c(15:30), sep="") 
 set2
 
 #  intersect two vectors  
 set1 %>% dplyr::intersect(.,set2)
 
 # union two vectors  WITHOUT duplicates
 set1 %>% dplyr::union(.,set2)
 
 # union two vectors  WITH duplicates
 set1 %>% dplyr::union_all(.,set2)
 
 #  difference of two vectors 
 set1 %>% setdiff(.,set2)
 ```
