# Handy bookmarklets

## Swap clipboard <=> textbox contents

Activate this bookmarklet with a text input in focus to exchange its contents with your clipboard contents.

```javascript
javascript:(async function () {let a = document.activeElement;if (a.type !== "text") {alert("A textbox is not currently selected");return;}let b = a.value;a.value = await navigator.clipboard.readText();await navigator.clipboard.writeText(b);})();
```

Expanded:

```javascript
(async function () {
  let a = document.activeElement;
  if (a.type !== "text") {
    alert("A textbox is not currently selected");
    return;
  }
  let b = a.value;
  a.value = await navigator.clipboard.readText();
  await navigator.clipboard.writeText(b);
})();
```

## Set the page zoom independently of other tabs or windows

In most browsers, adjusting a page's zoom will also adjust the zoom for that entire domain across all tabs and windows. If you'd prefer to adjust each tab independently, you can activate this bookmarklet.

This will not work in Firefox, which has not implemented the non-standard CSS zoom property.

```javascript
javascript:void(document.body.style.zoom="150%")
```

## Prevent text inputs stealing focus to their content

```javascript
javascript:(function() {for (let e of document.querySelectorAll('input[type="text"]')) { e.onclick = null;}})()
```

