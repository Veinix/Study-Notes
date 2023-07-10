# Client Side Storage Notes

There are a couple different ways to store data on the client. These include:

* Session Storage
* Local Storage
* Cache
* IndexDB
* Cookies

Definitions and further informations regarding these can be found below.

[Back to JavaScript Menu](./jsMain.md)

[Links to Sources](#sources)

---

## Session Storage

Maintains a separate storage area for each given origin that's available for the duration of the page session (as long as the browser is open, including page reloads and restores).
Stores data only for a session, meaning that the data is stored until the browser (or tab) is closed.
Data is never transferred to the server.
Storage limit is larger than a cookie (at most 5MB).

## Local Storage

Does the same thing as `sessionStorage`, but persists even when the browser is closed and reopened.
Stores data with no expiration date, and gets cleared only through JavaScript, or clearing the Browser cache / Locally Stored Data.
Storage limit is the maximum amongst the two.

## Methods

`getItem()`
: Getting an item from localStorage

`removeItem()`
: Removing an item from localStorage

`clear()`
: Clear all data from localStorage

`key()`
: Pass a number to retrieve the key of a localStorage

## Storage Event

We can listen to storage changes on the browser for both localStorage and sessionStorage. The storage event is fired when an item is created, deleted or updated. The listener function is passed in the event with the following properties:

`newValue`
: Value passed to setItem() when we create or update an item in storage. This value is set to null when we remove the item from storage.

`oldValue`
: Value of the item previously if the key exists in the storage when creating a new item.

`key`
: Key of the item that is being changed, value is null if .clear() is called.

`url`
: URL for which the storage action was performed.

`storageArea`
: Storage object on which the action was performed (localStorage or sessionStorage).

We can set storage event listeners either by using `window.addEventListener("storage", func)` or by using the `onstorage` attribute like so `window.onstorage = func`.

Example of alerting when an item is saved and its new/old value:

```javascript
window.onstorage = (event) => {
    if (event.key === "title"){
        alert(`your new title is ${event.newValue} the previous was ${event.oldValue}`)
    }
        alert('SAVED!!');
    }

localStorage.setItem("title", "kelly")
```

Note that the function won’t be triggered on the same tab where the change occurred. The function would be triggered by other opened tabs or windows of the same domain. This feature is used to sync data on all tabs/windows of the same domain. So to test this, you might want to open another tab of the same domain.

## Limitations of localStorage

`localStorage`

* Can only store data up to 5 MB. Ensure the data you are trying to store won’t exceed this limit.
* Only stores string data. To store JavaScript objects and arrays, serialize them into JSON strings, then store them. To retrieve the objects, deserialize them to get the object. Use `JSON.stringify()` to serialize objects and `JSON.parse()` to deserialize a JSON string to an object
* Data stored in localStorage is not accessible to web workers. (Web Workers makes it possible to run a script operation in a background thread separate from the main execution thread of a web application. The advantage of this is that laborious processing can be performed in a separate thread, allowing the main (usually the UI) thread to run without being blocked/slowed down)
* localStorage is synchronous (operations are executed one at a time)

Example of data exceeding storage limit

```javascript
localStorage.setItem('a', Array(1024 *1024* 5).join('a'))

localStorage.setItem('b', 'a')
```

```console
Uncaught DOMException: Failed to execute 'setItem' on 'Storage': Setting the value of `a` exceeded the quota.
```

In the example above, we get an error because we created a string that is 5 MB large, which is the max value we can store, so adding any more data would exceed that limit

## Security Vulnerabilities of Local Storage

* Can be exploited by XSS attacks. Sensitive information shouldn’t be stored in local storage

* Restricts developer access to data, as there is no server-side storage. Information is stored in the browser

## When To Use Local Storage

* Size of data is known. Ensure it doesn’t exceed 5 MB
* Storing non-sensitive data
* Data is String datatype or can be serialized and deserialized to strings easily

---

## Sources

<https://www.telerik.com/blogs/javascript-local-storage-all-you-need-know>

<https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API>

<https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage>

Web Workers (Relevant to Local Storage)

<https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API>

<https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers>

JavaScript Runtime Environment and Call Stack

<https://www.scaler.com/topics/synchronous-and-asynchronous-javascript/>

<https://medium.com/@gemma.croad/understanding-the-javascript-runtime-environment-4dd8f52f6fca>

<https://vahid.blog/post/2021-03-21-understanding-the-javascript-runtime-environment-and-dom-nodes/>

<https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/>

<https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide/In_depth>

<https://developer.mozilla.org/en-US/docs/Glossary/Call_stack>

Events

<https://www.tutorialspoint.com/javascript/javascript_events.htm>

<https://developer.mozilla.org/en-US/docs/Web/API/Event>
