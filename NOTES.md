Original JTcl source code was modified in order to support iRule operators:

__iRule only operators__

- *starts_with* Tests if one string starts with another string
- *ends_with* Tests if one string ends with another string
- *contains* Tests if one string contains another string
- *matches_glob* Implement glob style matching within a comparison
- *matches_regex* Tests if one string matches a regular expression

__iRule aliases to standard Tcl operators__

- *equals* Tests if one string equals another string (*eq* operator)
- *and* Performs a logical "and" comparison between two values (*&&* operator)
- *or* Performs a logical "or" comparison between two values (*||* operator)
- *not* Performs a logical "not" on a value (*!* operator)

The only files that have been modified are:

- Expr.java
- expr.test