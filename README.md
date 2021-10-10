# nodejs_coverage_bug

```
$ bazel coverage //...
INFO: Using default value for --instrumentation_filter: "^//test1[/:],^//test2/blah[/:]".
INFO: Override the above default with --instrumentation_filter
INFO: Analyzed 9 targets (0 packages loaded, 0 targets configured).
INFO: Found 7 targets and 2 test targets...
INFO: LCOV coverage report is located at /path/to/file
 and execpath is bazel-out/_coverage/_coverage_report.dat
INFO: Elapsed time: 0.057s, Critical Path: 0.00s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
//test1:test                                                    (cached) PASSED in 0.3s
  /path/to/file
//test2/blah:test                                               (cached) PASSED in 0.3s
  /path/to/file

Executed 0 out of 2 tests: 2 tests pass.
INFO: Build completed successfully, 1 total action
$ 
$ cat bazel-out/_coverage/_coverage_report.dat 
SF:../../main.test.ts
FNF:0
FNH:0
BRDA:1,0,0,1
BRDA:2,1,0,1
BRF:2
BRH:2
DA:1,1
DA:2,1
DA:3,1
DA:4,1
DA:5,1
LH:5
LF:5
end_of_record
SF:test2/blah/main.test.ts
FNF:0
FNH:0
BRDA:1,0,0,1
BRDA:2,1,0,1
BRF:2
BRH:2
DA:1,1
DA:2,1
DA:3,1
DA:4,1
DA:5,1
LH:5
LF:5
end_of_record
$
```

😟

```
SF:../../main.test.ts
```

should be

```
SF:test1/main.test.ts
```
