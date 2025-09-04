# Code
```
public fun main() {
	var s = (x: 4, y: 5)
	inout t = &s.0
	_ = t
	//print(s.0)
	&t = 8
	print(s.0)
}
```

# IR
```
// test.main
// test.hylo:1.1-8:2
external fun FunctionDecl(1835010)() -> {} {
b0(%b0#0 : &{}):
  %i0.0: &{x: Int, y: Int} = alloc_stack {x: Int, y: Int}
  %i0.2: &word = subfield_view %i0.0, 0, 0
  %i0.3: &word = access [set] %i0.2
  store i64(0x4), %i0.3
  end_access %i0.3
  %i0.6: &word = subfield_view %i0.0, 1, 0
  %i0.7: &word = access [set] %i0.6
  store i64(0x5), %i0.7
  end_access %i0.7
  %i0.9: &Int = subfield_view %i0.0, 0
  %i0.10: &Int = access [sink] %i0.9
  %i0.11: &Int = alloc_stack Int
  %i0.13: &Int = access [set] %i0.11
  memory_copy %i0.10, %i0.13
  end_access %i0.13
  mark_state deinitialized %i0.10
  mark_state deinitialized %i0.11
  %i0.19: &Int = alloc_stack Int
  %i0.20: &word = subfield_view %i0.19, 0
  %i0.21: &word = access [set] %i0.20
  store i64(0x8), %i0.21
  end_access %i0.21
  %i0.23: &Int = access [sink] %i0.19
  %i0.24: &Int = access [set] %i0.10
  memory_copy %i0.23, %i0.24
  end_access %i0.24
  end_access %i0.10
  mark_state deinitialized %i0.23
  end_access %i0.23
  %i0.29: &{} = alloc_stack {}
  %i0.30: &Int = subfield_view %i0.0, 0
  %i0.31: &Int = access [let] %i0.30
  %i0.32: &Int = alloc_stack Int
  %i0.33: &word = subfield_view %i0.32, 0
  %i0.34: &word = access [set] %i0.33
  store i64(0xa), %i0.34
  end_access %i0.34
  %i0.36: &Int = access [let] %i0.32
  %i0.37: &String = alloc_stack String
  %i0.38: i64 = constant_string "\n"
  %i0.39: &UInt64 = subfield_view %i0.37, 0, 0
  %i0.40: &UInt64 = access [set] %i0.39
  store %i0.38, %i0.40
  end_access %i0.40
  %i0.43: &String = access [let] %i0.37
  %i0.44: &{} = access [set] %i0.29
  call @FunctionDecl(911867904)(%i0.31, %i0.36, %i0.43) to %i0.44
  end_access %i0.43
  end_access %i0.36
  end_access %i0.31
  end_access %i0.44
  mark_state deinitialized %i0.29
  %i0.60: &{} = alloc_stack {}
  %i0.61: &{} = access [set] %i0.60
  %i0.62: &String = access [sink] %i0.37
  call @ConformanceDecl(821035008).(String).deinitialize(%i0.62) to %i0.61
  end_access %i0.62
  end_access %i0.61
  mark_state deinitialized %i0.60
  dealloc_stack %i0.60
  dealloc_stack %i0.37
  mark_state deinitialized %i0.32
  dealloc_stack %i0.32
  dealloc_stack %i0.29
  dealloc_stack %i0.19
  dealloc_stack %i0.11
  mark_state deinitialized %i0.0
  dealloc_stack %i0.0
  mark_state initialized %b0#0
  return
}

// Hylo.print(_:radix:terminator:)
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Print.hylo:9.1-32:2
external fun FunctionDecl(911867904)(let Int, let Int, let String) -> {}

// ConformanceDecl(821035008).(String).deinitialize
external fun ConformanceDecl(821035008).(String).deinitialize(sink String) -> {}
```