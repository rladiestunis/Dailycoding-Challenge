#create object on R with one of the operators (<-,=)
x=3
a="lotus"
z<-TRUE

#Display of the value of x
x

#Display of the value of a  
print(a)  

##Note:If an object does not exist the assignment creates it. Otherwise the assignment overwrites the previous value .
x=4  
x

##the different modes of an object (null,numeric,logical,character,complex) 
mode(x)  

mode(a)  
mode(z)  

  
#Conversion from one mode to another explicitly 
x=as.complex(x)  
x  

z=as.numeric(z)  
z  


#Implicit conversions from one mode to another are done in this order (logical,numeric,complex,character)
  
a=as.complex(a)
a

#Note:NA is a missing value
  
#Deleting objects
rm(a)  
a  
rm(x,z)  
x
