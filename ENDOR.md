//Find Bazel targets

bazel query //...

//Find all go binaries

bazel query 'kind(go_binary, //...)'

//Build a package

bazel build //pkg/cmd/cockroach-sql:cockroach-sql

//Scan two packages (bazel targets)

endorctl scan --use-bazel --bazel-include-targets=//pkg/cmd/cockroach:cockroach,//pkg/cmd/cockroach-sql:cockroach-sql

//Scan targets

endorctl scan --use-bazel --bazel-targets-query='kind(go_binary, //...)'

Core Product Binaries
//pkg/cmd/cockroach:cockroach - The main CockroachDB server binary (includes the SQL shell and all server functionality)
//pkg/cmd/cockroach-sql - Standalone SQL client shell
//pkg/cmd/workload - Load testing/benchmarking tool (published but separate from main release)