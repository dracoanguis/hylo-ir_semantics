# Code
```
public fun main() {
	print("Hello World!")
}
```

# IR
```
// test.main
// test.hylo:1.1-3:2
external fun FunctionDecl(196610)() -> {} {
b0(%b0#0 : &{}):
  %i0.0: &String = alloc_stack String
  %i0.1: i64 = constant_string "Hello World!"
  %i0.2: &UInt64 = subfield_view %i0.0, 0, 0
  %i0.3: &UInt64 = access [set] %i0.2
  store %i0.1, %i0.3
  end_access %i0.3
  %i0.6: &String = access [let] %i0.0
  %i0.7: &String = alloc_stack String
  %i0.8: i64 = constant_string "\n"
  %i0.9: &UInt64 = subfield_view %i0.7, 0, 0
  %i0.10: &UInt64 = access [set] %i0.9
  store %i0.8, %i0.10
  end_access %i0.10
  %i0.13: &String = access [let] %i0.7
  %i0.14: &{} = access [set] %b0#0
  call @FunctionDecl(903610368)(%i0.6, %i0.13) to %i0.14
  end_access %i0.13
  end_access %i0.6
  end_access %i0.14
  %i0.22: &{} = alloc_stack {}
  %i0.23: &{} = access [set] %i0.22
  %i0.24: &String = access [sink] %i0.7
  call @ConformanceDecl(821035008).(String).deinitialize(%i0.24) to %i0.23
  end_access %i0.24
  end_access %i0.23
  mark_state deinitialized %i0.22
  dealloc_stack %i0.22
  dealloc_stack %i0.7
  %i0.30: &{} = alloc_stack {}
  %i0.31: &{} = access [set] %i0.30
  %i0.32: &String = access [sink] %i0.0
  call @ConformanceDecl(821035008).(String).deinitialize(%i0.32) to %i0.31
  end_access %i0.32
  end_access %i0.31
  mark_state deinitialized %i0.30
  dealloc_stack %i0.30
  dealloc_stack %i0.0
  return
}

// Hylo.print(_:terminator:)
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Print.hylo:2.1-6:2
external fun FunctionDecl(903610368)(let String, let String) -> {}

// ConformanceDecl(821035008).(String).deinitialize
external fun ConformanceDecl(821035008).(String).deinitialize(sink String) -> {}
```