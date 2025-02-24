# Silent Errors with Missing Map Keys in Go

This repository demonstrates a common, yet subtle, error in Go: accessing a non-existent key in a map.  Unlike some other languages, Go does not raise an exception or panic when you try to access a key that's not present. Instead, it simply returns the zero value for the map's value type. This can lead to unexpected behavior and hard-to-debug errors.

The `bug.go` file shows the problem. Accessing the key "a" in the map `m` (which is initially empty) will not result in a runtime panic; instead, it will return 0. This might be unexpected if you're not aware of Go's map behavior.

The `bugSolution.go` file demonstrates how to handle this issue safely, checking for the key's existence before accessing the value.