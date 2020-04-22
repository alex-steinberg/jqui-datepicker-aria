# Make jQuery UI Datepicker more accessible

We are attempting to add an ARIA live region which reads the date currently on hover back to the visually impaired user.

The problem I'm having is hooking into an event to read which element the user currently has in focus. I suspect jQuery UI has performed `stopPropagation()` on all events. Had they not, this should work, for example: 

```
$(".ui-datepicker-calendar").on("focusin", updateRegion);
```

The picker's `onSelect` method only fires once the selection has been made, not when the user is still scrolling through the dates.

Seeing as the user can just enter the date in manually, I don't see this as a big problem to solve.