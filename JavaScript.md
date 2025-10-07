# Modern JavaScript Barebones Guide (.md)

## Core Concepts
- **Values:** `undefined`, `null`, `boolean`, `number`, `bigint`, `string`, `symbol`, `object`.
- **Declarations:** `const` (immutable binding), `let` (block), `var` (function; avoid).
- **Functions:** `function f() {}`, `const f = () => {}`; default/rest `f(a=1, ...rest)`.
- **Modules:** `export`, `export default`, `import x from './x.js'`.
- **This/Bind:** Arrow funcs don’t bind `this`; use for callbacks.
- **Equality:** Use `===`/`!==`; avoid `==`.
- **Async:** `Promise`, `async/await`, `try/catch`.

## Types & Utils
```js
const n = Number('42');         // parse number
const j = JSON.parse('{"a":1}');
const s = JSON.stringify({a:1});
Array.isArray([1,2]);
Object.keys(obj); Object.entries(obj); Object.assign({}, a, b);
```

## Control Flow
```js
if (x) {} else {}
for (const v of arr) {}
for (const k in obj) {}
while (cond) {}
switch (x) { case 1: break; default: }
try { /* ... */ } catch (e) { /* ... */ } finally {}
```

## Collections
```js
const arr = [1,2,3].map(x=>x*2).filter(x=>x>2).reduce((a,b)=>a+b,0);
const set = new Set([1,2,2]);            // unique
const map = new Map([['k','v']]);        // key→value
const weakMap = new WeakMap();           // GC’d keys (objects)
const weakSet = new WeakSet();
```

## Async Patterns
```js
const sleep = ms => new Promise(r => setTimeout(r, ms));
async function run() {
  try {
    const r = await fetch('/api');
    const data = await r.json();
  } catch (e) { /* handle */ }
}
Promise.all([p1, p2]); Promise.race([p1, p2]);
```

## DOM Basics
```js
const el = document.querySelector('#id');
el.textContent = 'Hello';
el.classList.add('active');
el.addEventListener('click', e => { e.preventDefault(); });
document.createElement('div');
```

## Events
```js
document.addEventListener('keydown', e => {
  if (e.key === 'Escape') { /* ... */ }
}, { passive: true });
```

## Fetch & Network
```js
const r = await fetch('/data.json', { method: 'POST', headers: {'Content-Type':'application/json'}, body: JSON.stringify({a:1}) });
if (!r.ok) throw new Error(r.statusText);
const data = await r.json();
```

## Storage
```js
localStorage.setItem('k', 'v');
sessionStorage.getItem('k');
await caches.open('v1'); // Cache Storage (Service Worker)
```

## Modules (ESM)
```html
<script type="module">
  import { sum } from './util.js';
  console.log(sum(1,2));
</script>
```

## Error Handling
```js
class AppError extends Error {
  constructor(msg, code) { super(msg); this.name='AppError'; this.code=code; }
}
```

## Common Built-in Classes (Core)
- Primitives wrappers: `String`, `Number`, `Boolean`, `Symbol`, `BigInt`
- Data/Collections: `Object`, `Array`, `Map`, `Set`, `WeakMap`, `WeakSet`
- Typed arrays: `ArrayBuffer`, `DataView`, `Uint8Array`, `Float32Array`, etc.
- Text/Intl: `RegExp`, `Date`, `Intl.*`, `URL`, `URLSearchParams`
- Errors: `Error`, `TypeError`, `RangeError`, `SyntaxError`, `ReferenceError`, `AggregateError`
- Promises/Control: `Promise`, `Generator`, `AsyncGenerator`, `Proxy`, `Reflect`
- JSON/Math: `JSON`, `Math`
- Structured clone: `structuredClone`

## Common Web Platform Classes/APIs
- DOM: `Node`, `Element`, `HTMLElement`, `Document`, `DocumentFragment`, `DOMParser`, `MutationObserver`, `IntersectionObserver`, `ResizeObserver`
- Events: `Event`, `CustomEvent`, `MouseEvent`, `KeyboardEvent`, `PointerEvent`, `AbortController`/`AbortSignal`
- Networking: `fetch`, `Request`, `Response`, `Headers`, `WebSocket`, `EventSource`
- URL: `URL`, `URLPattern` (where supported)
- Storage: `localStorage`, `sessionStorage`, `IndexedDB` (`indexedDB`, `IDBDatabase`, etc.)
- Workers: `Worker`, `SharedWorker`, `ServiceWorker` (in SW: `self`, `caches`, `clients`)
- Performance: `performance`, `PerformanceObserver`, `PerformanceEntry`
- Animation: `requestAnimationFrame`, `Animation`, `Web Animations API`
- Media: `MediaDevices` (`getUserMedia`), `MediaStream`, `HTMLMediaElement`
- Canvas/SVG: `CanvasRenderingContext2D`, `Path2D`, `SVGElement`
- Clipboard: `navigator.clipboard`
- Notifications: `Notification`
- Geolocation: `navigator.geolocation`
- Intl/Localization: `Intl.DateTimeFormat`, `Intl.NumberFormat`, `Intl.RelativeTimeFormat`
- Crypto: `crypto`, `SubtleCrypto` (`crypto.subtle`)
- File/Blob: `File`, `Blob`, `FileReader`, `FormData`, `DataTransfer`
- Scheduling: `setTimeout`, `setInterval`, `queueMicrotask`, `requestIdleCallback`

## Patterns/Snippets
```js
// Abortable fetch
const ac = new AbortController();
setTimeout(()=>ac.abort(), 5000);
const res = await fetch('/api', { signal: ac.signal });

// Debounce
const debounce = (fn, d=200) => {
  let t; return (...args) => { clearTimeout(t); t = setTimeout(() => fn(...args), d); };
};

// Deep clone (structured)
const clone = structuredClone(obj);

// DOM create/insert
const frag = new DocumentFragment();
['a','b','c'].forEach(t => {
  const li = document.createElement('li'); li.textContent = t; frag.append(li);
});
document.querySelector('ul').append(frag);
```

## Tooling Tips
- Use `type="module"` and defer bundlers when possible.
- Prefer `ESM` imports, `async/await`, `AbortController`, and `URL`.
- Lint/type with ESLint + JSDoc or TypeScript for DX.

## References (MDN)
- Language: https://developer.mozilla.org/docs/Web/JavaScript
- Built-ins: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects
- DOM API: https://developer.mozilla.org/docs/Web/API/Document_Object_Model
- Fetch API: https://developer.mozilla.org/docs/Web/API/Fetch_API
- Events: https://developer.mozilla.org/docs/Web/API/Event
- WebSockets: https://developer.mozilla.org/docs/Web/API/WebSocket
- Storage (Web): https://developer.mozilla.org/docs/Web/API/Web_Storage_API
- IndexedDB: https://developer.mozilla.org/docs/Web/API/IndexedDB_API
- Workers: https://developer.mozilla.org/docs/Web/API/Web_Workers_API
- Service Workers: https://developer.mozilla.org/docs/Web/API/Service_Worker_API
- Cache Storage: https://developer.mozilla.org/docs/Web/API/Cache
- Performance: https://developer.mozilla.org/docs/Web/API/Performance_API
- Web Animations: https://developer.mozilla.org/docs/Web/API/Web_Animations_API
- Media/Streams: https://developer.mozilla.org/docs/Web/API/MediaDevices
- Clipboard: https://developer.mozilla.org/docs/Web/API/Clipboard
- Notifications: https://developer.mozilla.org/docs/Web/API/Notifications_API
- Geolocation: https://developer.mozilla.org/docs/Web/API/Geolocation_API
- Intl: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl
- Crypto: https://developer.mozilla.org/docs/Web/API/Web_Crypto_API
- Canvas: https://developer.mozilla.org/docs/Web/API/Canvas_API
- SVG: https://developer.mozilla.org/docs/Web/SVG
- URL/URLSearchParams: https://developer.mozilla.org/docs/Web/API/URL
- URLPattern: https://developer.mozilla.org/docs/Web/API/URLPattern
- Forms/FormData: https://developer.mozilla.org/docs/Web/API/FormData
- Streams: https://developer.mozilla.org/docs/Web/API/Streams_API
