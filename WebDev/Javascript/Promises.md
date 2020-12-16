A Promise is an object representing the eventual completion or failure of an asynchronous operation. 
```
const promise = createAudioFileAsync(audioSettings); 
promise.then(successCallback, failureCallback);
```

Callbacks will never be called before the completion of the current run of the JavaScript event loop.
Callbacks added with then(), as above, will be called even after the success or failure of the asynchronous operation.
Multiple callbacks may be added by calling then() several times. Each callback is executed one after another, in the order in which they were inserted.


## Chaining

const promise2 = doSomething().then(successCallback, failureCallback);

```
doSomething()
.then(result => doSomethingElse(result))
.then(newResult => doThirdThing(newResult))
.then(finalResult => {
  console.log(`Got the final result: ${finalResult}`);
})
.catch(failureCallback);
```
Important: Always return results, otherwise callbacks won't catch the result of a previous promise (with arrow functions () => x is short for () => { return x; }).

It's possible to chain after a failure


Promise.resolve() and Promise.reject() are shortcuts to manually create an already resolved or rejected promise respectively. This can be useful at times.

Promise.all() and Promise.race() are two composition tools for running asynchronous operations in parallel.


[func1, func2, func3].reduce((p, f) => p.then(f), Promise.resolve())
.then(result3 => { /* use result3 */ });

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises