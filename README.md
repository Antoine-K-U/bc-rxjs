# bc-rxjs

## Presentation

### Intro
- tableau Sync/Async & Unique value/Collection -> Obserbable http://reactivex.io/intro.html
- promises vs Observable
- Observables & Observers
 - Observable behaviour => emit 0 to N values. Completes or not. End in error or not.

### Pratique
- Creation : of, just, interval, events,request, web sockets...
- Syntaxe .subsribe
- Operators: grouper par catégorie ?
 - map, filter, delay, flatmpap, combineLatest, merge, aggregate, scan, take, retry, buffer, sample

### Advanced
- Divers: 
 - Pipeline
 - no subscribe / no code executed
 - lazy
 - Observable immutable
- Hot/Cold observables (+warm observables) ...
- Bonnes pratiques
 - pure functions
 - side effects, only in subscribes
 - naming convention: myobervable$
 - Beware Subjects, often misused
- Scheduler
- Unit tests
- Debugging (new of 5.0.0, .do log)
- Observable are abortbable (vc promises)

### Autres/Bonus
- MVI
- Clojure
- akka

### Sources/Links
