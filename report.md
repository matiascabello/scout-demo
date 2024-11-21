
<style>
.markdown-body table {min-width: 100%;width: 100%;display: table;}
thead {min-width: 100%;width: 100%;}
th {min-width: 60%;width: 60%;}
th:last-child {min-width: 20%;width: 20%;}
th:first-child {min-width: 20%;width: 20%;}
</style>


# Scout Report - Scout Demo - 2024-11-21

## Summary

| <span style="color:green">Crate</span> | <span style="color:green">Status</span> | <span style="color:green">Critical</span> | <span style="color:green">Medium</span> | <span style="color:green">Minor</span> | <span style="color:green">Enhancement</span> | 
| - | - | - | - | - | - | 
| governance | Analyzed | 8 | 5 | 0 | 4 | 


Issues found:


- [Integer Overflow/Underflow](#integer-overflow/underflow) (8 results) (Critical)
- [Unsafe Unwrap](#unsafe-unwrap) (2 results) (Medium)
- [Assert Violation](#assert-violation) (3 results) (Medium)
- [Storage change event checker](#storage-change-event-checker) (3 results) (Enhancement)
- [Check Soroban version](#check-soroban-version) (1 results) (Enhancement)



## Arithmetic



### Integer Overflow/Underflow

**Impact:** Critical

**Issue:** Potential for integer arithmetic overflow/underflow. Consider checked, wrapping or saturating arithmetic.

**Description:** An overflow/underflow is typically caught and generates an error. When it is not caught, the operation will result in an inexact result which could lead to serious problems.

[**Learn More**](https://coinfabrik.github.io/scout-soroban/docs/vulnerabilities/integer-overflow-or-underflow)

#### Findings

| ID  | Package | File Location |
| --- | ------- | ------------- |
| 4 | src | [lib.rs:124:9 - 124:30](src/lib.rs) |
| 5 | src | [lib.rs:134:30 - 134:55](src/lib.rs) |
| 6 | src | [lib.rs:177:13 - 177:41](src/lib.rs) |
| 7 | src | [lib.rs:179:13 - 179:41](src/lib.rs) |
| 8 | src | [lib.rs:194:27 - 194:76](src/lib.rs) |
| 9 | src | [lib.rs:195:40 - 195:76](src/lib.rs) |
| 10 | src | [lib.rs:197:12 - 197:56](src/lib.rs) |
| 11 | src | [lib.rs:205:20 - 205:79](src/lib.rs) |



## Validations and error handling



### Unsafe Unwrap

**Impact:** Medium

**Issue:** Unsafe usage of `unwrap`

**Description:** This vulnerability class pertains to the inappropriate usage of the unwrap method in Rust, which is commonly employed for error handling. The unwrap method retrieves the inner value of an Option or Result, but if an error or None occurs, it triggers a panic and crashes the program.    

[**Learn More**](https://coinfabrik.github.io/scout-soroban/docs/detectors/unsafe-unwrap)

#### Findings

| ID  | Package | File Location |
| --- | ------- | ------------- |
| 12 | src | [lib.rs:203:34 - 203:73](src/lib.rs) |
| 13 | src | [lib.rs:240:24 - 244:22](src/lib.rs) |



## Panic



### Assert Violation

**Impact:** Medium

**Issue:** Assert causes panic. Instead, return a proper error.

**Description:** Assert causes panic. Instead, return a proper error.

[**Learn More**](https://coinfabrik.github.io/scout-soroban/docs/detectors/assert-violation)

#### Findings

| ID  | Package | File Location |
| --- | ------- | ------------- |
| 0 | src | [lib.rs:90:28 - 90:55](src/lib.rs) |
| 1 | src | [lib.rs:162:9 - 162:50](src/lib.rs) |
| 2 | src | [lib.rs:190:9 - 190:69](src/lib.rs) |



## Best Practices



### Storage change event checker

**Impact:** Enhancement

**Issue:** 

**Description:** Emiting an event when storage changes is a good practice to make the contracts more transparent and usable to its clients and observers

[**Learn More**](https://coinfabrik.github.io/scout-soroban/docs/detectors/storage-change-events)

#### Findings

| ID  | Package | File Location |
| --- | ------- | ------------- |
| 14 | src | [lib.rs:110:5 - 116:30](src/lib.rs) |
| 15 | src | [lib.rs:70:5 - 77:30](src/lib.rs) |
| 16 | src | [lib.rs:147:5 - 152:30](src/lib.rs) |



## Best practices



### Check Soroban version

**Impact:** Enhancement

**Issue:** Use the latest version of Soroban

**Description:** Using a older version of Soroban can be dangerous, as it may have bugs or security issues. Use the latest version available.

[**Learn More**](https://coinfabrik.github.io/scout-soroban/docs/detectors/soroban-version)

#### Findings

| ID  | Package | File Location |
| --- | ------- | ------------- |
| 3 | src | [lib.rs:1:1 - 1:1](src/lib.rs) |


