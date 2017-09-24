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
