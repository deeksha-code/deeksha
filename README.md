##
##I simply set the input X as a matrix
##and then set the solved value "s" as a null
##then I changed every reference to "mean" to "solve"
makeCacheMatrix <- Function(x=matrix(sample(1:100,9),3,3)){
 s <- NULL
 set <- function(Y) {
  x <<- y
  s <<- NULL
 }
 get <- function() x
 setsolve <- function(solve) s <<- solve
 getsolve <- function() s
 list(set = set , get =get ,
      setsolve = setsolve
      getsolve = getsolve
  }
  ##
  ## same here changed "mean" to "solve" and "n" to "s"
  cachesolve <- function(x, ...) {
    s<- X$getsolve()
    if(!is.null(s)) {
         message("getting inversed matrix")
          return(s)
     }
     data <- x$get()
     s <- solve(data,...)
     x$setsolve(s)
     s
}
