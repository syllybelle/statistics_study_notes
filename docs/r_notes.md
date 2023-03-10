?> learning R from a python background

# R  functions
 
`c(a, b, ..)`:         combine/concat/create vector/list from items a, b, ..  
`character(a)`: convert `a` to string, or convert iterations in an interable to string type  
`rbind(data, c)`:     add row vector `c` to a dataframe `data`
`combinat::permn(c)` : return all permutations of vector/list `c` as vector
`gtools::combinations(n, r)` : generate a vector of combinations where r objects are picked from a set of size n 

`length(combinat::permn(c))` = $c!$  
`length(gtools::combinations(n, r))` = $n \choose r$ (binomial coefficient ) 
`set.seed(i)` = set the randomisation seed
`rep(x, ...)` : replicates values in 'x' '...'  times'. there are a number of arguments, but with an int listed it will output a 1d array
`runif(1)`: generate random number from a uniform distribution between 0 and 1 (e.g. 0.614549)
`x.y`: create and assign property `y` to variable/object `x`
