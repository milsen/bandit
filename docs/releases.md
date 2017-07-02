# Releases

For a list of releases including release notes, go to
[bandit's releases page on GitHub](//github.com/banditcpp/bandit/releases).

Bandit will be using [Semantic Versioning 2.0.0](http://semver.org/spec/v2.0.0.html)
beginning from the next major release v3.0.0.
In the following, we list breaking changes per major release.

## Next major release (v3.0.0)

* In prior versions, an error was raised in case no tests were available
  or all tests were skipped. Now the exit code is `0` in these cases because
  no tests are failing.

* The behavior of combined `--only` and `--skip` has changed.
  You can now use these switches multiple times and they always act as a filter,
  that is, you can only reduce the list of tests by adding a `--only` or `--skip`
  switch.
  In prior versions, contexts matching `--skip` were ignored when they contained
  a matching `--only`.

* The option handling became stricter.
  Illegal option arguments like `--reporter=invalid` result in an error now.

* The assertion framework Snowhouse v3.0.0 is used including all its breaking
  changes.

* The `snowhouse` namespace is not used by default.
  To make your old code compile, it may be necessary to add
  ```c++
  using namespace snowhouse;
  ```