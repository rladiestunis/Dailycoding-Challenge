## Day 24 of #dailycoding challenge ⬇️

Today we are interested in R- Decision Tree :
Decision tree is a graph to represent choices and their results in form of a tree. The nodes in the graph represent an event or choice and the edges of the graph represent the decision rules or conditions.
Generally, a model is created with observed data also called training data. Then a set of validation data is used to verify and improve the model.

🟪 The R package "party" is used to create decision trees.

🟪 The package "party" has the function ctree() which is used to create and analyze decison tree :

🔹 Syntaxe : ctree(formula, data)

- formula is a formula describing the predictor and response variables.

- data is the name of the data set used.

◼️ We will use the R in-built data set named readingSkills to create a decision tree. It describes the score of someone's readingSkills if we know the variables "age","shoesize","score" and whether the person is a native speaker or not.

Take a look at the examples below to understand more the use of the R -Decision Tree ⬇️

Happy Coding Learning !

``` r
#Install package party
install.packages("party")
# Load the party package. It will automatically load other dependent packages.
library(party)

# Print some records from data set readingSkills.
print(head(readingSkills))

#We will use the ctree() function to create the decision tree and see its graph.
# Load the party package. It will automatically load other dependent packages.
library(party)

# Create the input data frame.
input.dat <- readingSkills[c(1:105),]

# Give the chart file a name.
png(file = "decision_tree.png")

# Create the tree.
output.tree <- ctree(
  nativeSpeaker ~ age + shoeSize + score, 
  data = input.dat)

# Plot the tree.
plot(output.tree)

# Save the file.
dev.off()
#Conclusion
#From the decision tree shown above we can conclude that anyone whose readingSkills score is less than 38.3 and age is more than 6 is not a native Speaker.
```
