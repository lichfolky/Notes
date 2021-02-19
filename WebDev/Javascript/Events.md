

## Event
**target/srcElement** the original source of the event.
**currentTarget(this)** property. It contains a reference to the HTML element the event is currently being handled by.

capturing phase --> target --> bubbling phase

https://developer.mozilla.org/it/docs/Web/API/Element/addEventListener
https://www.w3.org/TR/DOM-Level-3-Events/#event-flow


https://www.quirksmode.org/js/events_order.html#link4

event.stopPropagation()
```
element1.addEventListener(
  "click",
  (event) => {
    event.stopPropagation();
  },
  true //  true the event handler is set for the capturing phase, false bubbling phase.
);
```

Note: useCapture non è sempre stato opzionale. Idealmente, dovresti includerlo per la massima compatibilità con i browser.


https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation
It does not, however, prevent any default behaviors from occurring.



https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault
event.preventDefault();

document.querySelector("#id-checkbox").addEventListener("click", function(event) {
         document.getElementById("output-box").innerHTML += "Sorry! <code>preventDefault()</code> won't let you check this!<br>";
         event.preventDefault();
}, false);
