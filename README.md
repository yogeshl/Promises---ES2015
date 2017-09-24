# Promises---ES2015
##Overview of promises
1. Managing multiple async operations via callbacks is very hard
2. Using many callback function is inefficient because
    a. Sharing data requires closures, and because closures require lexical scope , callback functions must be nested within each other
    b. Handling errors within multiple callbacks is difficult, can be very messy.
    c. Tracking multiple concurrent async operations requires a complex system of counters or other techiniques.
3. To solve the challenges posted by callbacks and multiple async callbacks, promises were created.

##Benefits of Promises
1. An API to manage both sequential and concurrent async operations.
2. A non-closure based approach to sharing data bw async operations.This prevents the endless nesting of callback functions.
3. An organized system of resolving and rejecting async operations which enables a easier and more effective error-handling mechanism.
4. A race API to select the result of two concurrent operations based upon which completes first.
5. Many implementations have existed for years through UI libraries and frameworks such as dojo, Q, jquery, AngularJS, Bluebird, etc.
6. Within Javascript, the Promise API runs as native code and javascript event loop queue system gives native promise tasks a higher priority for execution.
7. For async operations which yield a continuous  steam of data, Observables are a better solution (RxJS)

## Promise
1. Promises are  a proxy object for a value which is not necessarily known at the time  of promise was created.
2. The Promise essentially promises to deliver the value once it is known, which could be now i.e Sync or in the future i.e Async
3. The Promise class has 2 static functions - resolve and reject which can be used to produce a proxy object for a known value.
4. Promises go through 3 stages 
    a. pending - Created and waiting for resolve or reject to be called.
    b. fulfilled - resolve called
    c. rejected - reject called.

### Events vs Promise
1. A promise only resolves or rejects once, whereas events fire multiple times.
2. Promises produce one of two possible results: resolve and reject, events only have a single result.
3. Events are good example for an Observable, while REST service requests are a good example of a  Promise.

## Sequential Async Operations
1. Many times one async operation depends upon the data from the completion of another async operation
2. To code fot this relationship, the nesting of callback of functions is required.
3. When the callback for the  first operation executes, it launches the 2nd operation.
4. When chaining many async operations, managing the nesting of many async callback functions is challenging and results in the "pyramid of doom" issue.
5. Promises help solve this problem by allowing multiple async operations to be chained with the "then" function.


## Handling Async Errors
1. try,catch, finally - does not support async operations. It works with sync code only.
2. Traditional callback mechanism would either provide an error object parameter (ex. nodejs programming) in the call back function, or non Promise-API mechanism for registering the error callback function.
3. Both mechanisms are sufficient for a single async operation, but are difficult to use with multiple async operations.
4. With Promises, the concept of rejected promise lends itself to async error handling.
5. The "then" registered function represents the "try-block" and the "catch" registed function represents the "catch-block", the "finally-block" can be created with a final "then" registed function at the end of the promise chain.

