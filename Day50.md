## Day 50 #dailycoding challenge ⬇️

The starting point to program is the creation of objects that will be manipulated later in our project. This is why the code of today is about creating objects and controlling its modes.

The principal modes are "logical, numeric, complex and character".

we can convert the mode of an object to an other, but the conversion must respect this order :

logical

numeric

complex

character

A logical mode object can be converted to any other mode, but for example a numeric mode object can only be converted to complex or character.

Please take a look at the examples below to learn more ⬇️

```{r}
# create object on R with one of the operators (<-,=)
x = 3
a = "lotus"
z <- TRUE

# Display of the value of x
x

# Display of the value of a  
print(a)  

## Note : If an object does not exist the assignment creates it. Otherwise the assignment overwrites the previous value .
x = 4  
x

## the different modes of an object (null,numeric,logical,character,complex) 
mode(x)  

mode(a)  
mode(z)  

  
# Conversion from one mode to another explicitly 
x = as.complex(x)  
x  

z = as.numeric(z)  
z  

# Implicit conversions from one mode to another are done in this order (logical, numeric, complex, character)
  
a = as.complex(a)
a

# Note : NA is a missing value
  
# Deleting objects
rm(a)  
a  
rm(x,z)  
x
```
