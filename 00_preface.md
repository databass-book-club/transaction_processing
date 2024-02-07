# Preface - Why We Wrote this Book

In a nutshell: without transactions, distributed systems cannot be made to work for typical real-life applications.

In fact, some of the key ideas were developed way back when batch processing was in full swing, but they are far from being obsolete. Transaction processing concepts were conceived to master the complexity in single-processor online applications. If anything, these concepts are even more critical now for the successful implementation of massively distributed systems that work and fail in much more complex ways.

To make large systems work, one most adopt a genuine end-to-end attitude, starting at the point where a request comes in, going through all the system layers and components, and not letting go until the final result is safely delivered.

