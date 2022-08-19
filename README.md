# JSON Schema Vex Suite

This repository contains a set of vexatious JSON Schema objects which implementors of JSON Schema libraries can use to test their implementations.

This is in contrast to the [JSON Schema *Test* Suite](https://github.com/json-schema-org/JSON-Schema-Test-Suite), which contains schemas which conform to their specification, along with instances and expected validation outcomes. This repository contains nonconformant JSON Schemas. These schemas typically violate some MUST or MUST NOT directive of the relevant specification.

Schemas which are not conformant to their JSON Schema specification have undefined behavior. No particular outcome is expected, and this suite does not specify any outcome.

How an implementation handles these schemas is undefined, but worth testing. Does your implementation detect these errors in the schema and report them to the user? Does it silently ignore them, processing the schema but disregarding the nonconformant portions? Does it crash the entire application?

Uniformity is also not expected in how nonconformant schemas are handled. An implementation might, for example, treat a `"maxLength": -1` as a validation that considers every string invalid; the same implementation may encounter a stack overflow handling a circular `"$ref": "#"`. Neither is incorrect, nor is it incorrect to handle the cases differently, as no correct behavior is specified.

## Who Uses the Test Suite

This suite is being used by:

### Ruby

* [JSI](https://github.com/notEthan/jsi)

## Contributing

Issues and pull requests are welcome on GitHub at https://github.com/notEthan/JSON-Schema-Vex-Suite.
