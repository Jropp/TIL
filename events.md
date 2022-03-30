

```html
  <app-enter>
    <!-- Listener A.window -->
    <!-- Listener A.document -->
    <view-container>
      <!-- Listener B -->
      <sub-component>
        <!-- Event is dispatched from here -->
      </sub-component>
    </view-container>
  </app-enter>
```
## Capture

```js 
  // in app-enter
  window.addEventListener('clicky', (e) => null);
  document.addEventListener('clicky', (e) => null, true);

  // in sub-component
  this.dispatchEvent(new CustomEvent('clicky', {
    // Allows it to break through the shadow dom
    bubbles: true, 
    composed: true,
  }));

    this.dispatchEvent(new CustomEvent('clicky', {
      bubbles: false, 
      composed: true,
    }));

```


