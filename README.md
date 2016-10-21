# ProgrammingAssignment
ProgAssgn2
## Programming Assingment 2
## Data Science Specialization

## This function creates an object that stores a matrix, 
## then caches its inverse

## Matrix creation:

makeCacheMatrix <- function(x = matrix()) {
  inv <- NULL
  set <- function(z){
    x <<- z
    inv <<- NULL
  }


get <- function()x
setInverse <- function(inverse) inv <<- inverse
getInverse <- function() inv
list(set = set,
     get = get,
     setInverse = setInverse,
     getInverse = getInverse)
}

## The function above is used to compute the Inverse of a Matrix
## The fucntion below caches the result


cacheSolve <- function(x, ...) {
        ## Return a matrix that is the inverse of 'x'
  inv <- x$getInverse()
  if(!is.null(inv)){
    message("cached")
    return(inv)
  }
  mat <- x$get()
  
  inv <- solve(mat, ...)
  x$setInverse(inv)
  inv
}

## Usage example:
## x <- matrix(1:4, nrow=2, ncol=2)
## y <- makeCacheMatrix(x)
## z <- cacheSolve(y)
## print(z)
## z should return:
##     [,1] [,2]
##[1,]   -2  1.5
##[2,]    1 -0.5
##
## z2 <- cacheSolve(y)
## This should display a "cached" message
## print(z2)
## z2 should return
##     [,1] [,2]
##[1,]   -2  1.5
##[2,]    1 -0.5
