## Exercise 4

Goal: Profile a building block with additional rules, with tests

Note this illustrates how to use examples to test rules fail when expected. This is a critical capability for complex systems.

### Steps
- uncomment import from schema.yaml
- uncomment line #11 in rules.shacl and examine the additional profile constraint (B<5))
- run build
- run viewer
- navigate to "Exercise 4"/Validation
- view validation results on "about tab"
- move `examples/*-fail` to `tests`
- run build
- run viewer
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/template/exercise3/_report.json)