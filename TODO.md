
[X] sourcemaped error support for coffee-typer (debugging blind at the moment)

[X] class definitions
  [X] method: -> ...    --> method() { ... }
  [X] member: value     --> public member = value
  [X] @member: value    --> (public) static member = value
  [X] @method: -> ...   --> static method() { ... }
  [X] @member = value   --> static member = value
  [X] @method = -> ...  --> static method() { ... }
  [X] warn on everything else
  [X] allow bound methods
  [X] allow block comments

[X] method definitions
  [X] constructors (CS&TS treat them the same, just make them normal mehtods)
  [X] `public` parameters for constructors
  [X] static methods
  [X] `this` refers to the class object in static methods...?

[X] super (only calls current method on immediate super)
  [-] w/o arg: applies current args (not used in palantir codebase)
  [ ] consider static methods

[X] function definitions
  [X] default parameters
  [-] overloads (not in CoffeeScript; code that uses parameters as different types will need to be rewritten)
  [X] varargs (splats -> spreads, args... -> ...args)
  [X] pull out if in Assign
    - FIXME: remove extra semicolon after function definition

[ ] fat/thin arrow lambdas
  [ ] always use TS lambda on 'boundfunc', unless method (then what?)
  [ ] use TS lambda only on fat arrow, or where `this` is not used

[ ] for loop / comprehensions (.filter lam*, .map lam)
  [ ] arrays use: for value(, index) in array
  [ ] hashes use: for (own) key, value of dict

[ ] make utils stdlib things, us.bind
[ ] remove `Generated by CoffeeScript` header

[-] do construct (only used 3 times in Palantir code base)
[ ] in operator
  - should add Array.prototype.contains / Object.prototype.in, ask about polyfills

[ ] stop predeclaring variables; declare at first usage if possible
[ ] remove uses of _ref wherever possible
  [ ] existential operator [?]
  [ ] desugaring assignment [see CS docs]

[-] :: (prototype extension...) this just happens, see what tsc has to say about it

[X] @warn: log message, line of code, line numbers

[ ] check out best practices for ts org

[ ] modules
  [ ] `export` everything at root level by default


[ ] TypeScript requrires members to be declared
  [ ] read tsc's errors to find undeclared members... maybe this should be a separate tool...
  [ ] tsc doesn't try to guess the types of the members... for now maybe we should just use public