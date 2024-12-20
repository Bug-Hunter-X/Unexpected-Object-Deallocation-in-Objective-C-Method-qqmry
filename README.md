# Objective-C Memory Management Bug

This repository demonstrates a common error in Objective-C related to memory management and object deallocation. The bug occurs when an object is created and passed to a method without proper retention, leading to premature deallocation and potential crashes.

## Bug Description
The primary issue lies in the lack of proper handling of object ownership within a method.  An object is created, passed as an argument to a method that doesn't retain it, and then deallocated before it's no longer needed, causing subsequent accesses to produce unpredictable results.

## Solution
The solution involves ensuring that any object passed to a method that needs to use it after the method call must be retained using `retain` (or strong property in ARC).