# ProgrammingAssignment2
This is a repo for my second assigment
makeCacheMatrix <- function(x = numeric()) {
          makecache <- NULL
          setMatrix <- function(newValue) {
                x <<- newValue
                makecache <<- NULL
              }
  
            getMatrix <- function() {
                  x
              }
  
            cacheInverse <- function(solve) {
                    makecache <<- solve
              }
              
            getInverse <- function() {
                      makecache
            }
          
            list(setMatrix = setMatrix, getMatrix = getMatrix, cacheInverse = cacheInverse, getInverse = getInverse)
  }
  
    cacheSolve <- function(y, ...) {
            inverse <- y$getInverse()
            if(!is.null(inverse)) {
            message("getting cached data")
            return(inverse)
                }
            data <- y$getMatrix()
            inverse <- solve(data)
            y$cacheInverse(inverse)
            
            inverse
    }

