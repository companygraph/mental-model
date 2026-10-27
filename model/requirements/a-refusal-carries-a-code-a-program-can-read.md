---
id: 01a1312d-63fa-7a20-a5ca-a0b19b506c10
source: Local
kind: functional
modality: must
realization: Verified
---

# A refusal carries a code a program can read

> A call the server refuses carries a code for a program beside the sentence for a reader, and the codes and the schema of a refusal can be asked for.

## Why

An agent that is refused with a sentence alone has to guess what to do next, and a guess is where it repeats the call or gives up on a list it could have restarted. A code says which it is.

## Fit criterion

Every refused call carries a code; the tool that describes errors lists every code and the schema of a refusal; and a cursor from an earlier commit is refused with the code for an invalid cursor and the reason that it is from another commit, naming the commit now served.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent reads the model |

## Realization

Every refused call returns an error result whose structured content carries `error.code` from a closed list of nine, the sentence, the rule where one applies, and `details` under keys the code fixes, beside `model`. The `describe_errors` tool lists every code with when it is raised and serves the JSON Schema of a refusal and of each code's details. A cursor written for another commit is refused with `invalid_cursor` and `details.reason` of `other_commit`, and the sentence says it was written for another commit than the one now served. The commit now served is named by the `model.commit` every refusal carries; the sentence itself does not print the SHA. Tests in the release drive each code through a client, check that `describe_errors` lists exactly the closed list, read the served schema back with a separate validator and check it refuses a made-up code, and check the other-commit cursor case.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/contract.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/contract.test.mjs |
| `test/describe-errors.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/describe-errors.test.mjs |
| `lib/errors.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/lib/errors.mjs |

## References

| What | URL |
| --- | --- |
| The server's interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
