# bc-rxjs

## Presentation

### Intro
- Reactive programming -> Maxime Lemaître presentation last year 
- Treating all kind of events as one type (observable) and manupulating them with operators
- tableau Sync/Async & Unique value/Collection -> Obserbable http://reactivex.io/intro.html
- promises vs Observable
 - promise : get a single value, not lazy, immutable and uncancellable (only resolve or reject) => good for ajax calls (1 value)
  - toto.then(success, error);
 - observable : streams of events, lazy (produce a result only when subscribe) => good for DOM events, animations, WebSockets...
  - let sub = toto.subscribe(success, error, complete);
  - sub.unsubscribe(); => don't send me values anymore
- Observables & Observers
 - Observable behaviour => emit 0 to N values. Completes or not. End in error or not.

### Pratique
- Creation : of, from, fromEvent, just, interval, events,request, web sockets...
- Syntaxe .subscribe()
- Operators
 - example let result = source.myOperator(); => result is a new observable so result will emits values
 - Operators pass each value from one operator to the next, before proceeding to the next value in the stream, http://rxmarbles.com/
 - Basics : map, filter, reduce, first, last, single, elementAt...
 - Merging : merge, flatMap, concat, switch, combineLatest...
 - Grouping : groupBy...
 - Buffering : buffer, throttle, debounce, sample...
 - Many more : delay, scan, retry...
 
### Advanced
- Divers: 
 - Pipeline
 - no subscribe / no code executed
 - lazy
 - Observable immutable
- Hot/Cold observables (+warm observables) ...
 - Cold : create a new producer each time a consumer subscribes to them
 - Hot : share a single producer with every consumer that subscribes to them => share() operator
 
- Bonnes pratiques
 - pure functions
 - side effects, only in subscribes
 - naming convention: myobervable$
 - Beware Subjects, often misused
- Scheduler
- Unit tests
- Debugging (new of 5.0.0, .do log)
- Observable are abortbable (vc promises)

### Conclusion
- Angular2 is using RxJS massively -> show example from ng-europe
```javascript
 export class AppComponent {
  myControl = new FormControl();
  results:Observable <any[]>
  constructor(http: Http) {
   this.results = this.myControl.valueChanges
                     .map(text=>'http://api.com?q=${text}')
                     .switchMap(url=>http.get(url),(req,res)=>res.json())
   }
  }
 ```
 ```html
  <input type="text"[formControl]="myControl">
  <ul>
  <li *ngFor="r of results | async"> {{r.name}} </li>
  </ul>
 ```
### Autres/Bonus
- MVI
- Clojure
- akka

### Sources/Links
