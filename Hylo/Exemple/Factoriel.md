# Code
```
/// Computes the factorial of `n`.
///
/// - Requires: `n` must be greater or equal to 0.
fun factorial(_ n: Int) -> Int {
  if n < 2 { 1 } else { n * factorial(n - 1) }
}

public fun main() {
  let x = factorial(6)
  print(x)
}
```

# IR
```
// Hylo.print(_:radix:terminator:)
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Print.hylo:9.1-32:2
external fun FunctionDecl(911867904)(let Int, let Int, let String) -> {}

// ConformanceDecl(821035008).(String).deinitialize
external fun ConformanceDecl(821035008).(String).deinitialize(sink String) -> {}

// Hylo.infix*
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Core/Numbers/Integers/Int.hylo:150.3-152:4
external fun FunctionDecl(259588096)(let Int, let Int) -> Int

// Hylo.infix<
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Core/Numbers/Integers/Int.hylo:100.3-102:4
external fun FunctionDecl(250806272)(let Int, let Int) -> Bool

// test.main
// test.hylo:8.1-11:2
external fun FunctionDecl(2162690)() -> {} {
b0(%b0#0 : &{}):
  %i0.0: &Int = alloc_stack Int
  %i0.1: &Int = alloc_stack Int
  %i0.2: &word = subfield_view %i0.1, 0
  %i0.3: &word = access [set] %i0.2
  store i64(0x6), %i0.3
  end_access %i0.3
  %i0.5: &Int = access [let] %i0.1
  %i0.6: &Int = access [set] %i0.0
  call @FunctionDecl(1245186)(%i0.5) to %i0.6
  end_access %i0.5
  end_access %i0.6
  %i0.9: &Int = access [let] %i0.0
  %i0.10: &{} = alloc_stack {}
  %i0.12: &Int = alloc_stack Int
  %i0.13: &word = subfield_view %i0.12, 0
  %i0.14: &word = access [set] %i0.13
  store i64(0xa), %i0.14
  end_access %i0.14
  %i0.16: &Int = access [let] %i0.12
  %i0.17: &String = alloc_stack String
  %i0.18: i64 = constant_string "\n"
  %i0.19: &UInt64 = subfield_view %i0.17, 0, 0
  %i0.20: &UInt64 = access [set] %i0.19
  store %i0.18, %i0.20
  end_access %i0.20
  %i0.23: &String = access [let] %i0.17
  %i0.24: &{} = access [set] %i0.10
  call @FunctionDecl(911867904)(%i0.9, %i0.16, %i0.23) to %i0.24
  end_access %i0.23
  end_access %i0.16
  end_access %i0.9
  end_access %i0.24
  mark_state deinitialized %i0.10
  %i0.40: &{} = alloc_stack {}
  %i0.41: &{} = access [set] %i0.40
  %i0.42: &String = access [sink] %i0.17
  call @ConformanceDecl(821035008).(String).deinitialize(%i0.42) to %i0.41
  end_access %i0.42
  end_access %i0.41
  mark_state deinitialized %i0.40
  dealloc_stack %i0.40
  dealloc_stack %i0.17
  mark_state deinitialized %i0.12
  dealloc_stack %i0.12
  dealloc_stack %i0.10
  mark_state deinitialized %i0.1
  dealloc_stack %i0.1
  mark_state deinitialized %i0.0
  dealloc_stack %i0.0
  mark_state initialized %b0#0
  return
}

// Hylo.infix-
// /home/gargan/.cache/hylo-language-git/src/hylo/StandardLibrary/Sources/Core/Numbers/Integers/Int.hylo:128.3-130:4
external fun FunctionDecl(256638976)(let Int, let Int) -> Int

// test.factorial(_:)
// test.hylo:4.1-6:2
module fun FunctionDecl(1245186)(let Int) -> Int {
b0(%b0#0 : &Int, %b0#1 : &Int):
  %i0.0: &Bool = alloc_stack Bool
  %i0.1: &Int = alloc_stack Int
  %i0.2: &word = subfield_view %i0.1, 0
  %i0.3: &word = access [set] %i0.2
  store i64(0x2), %i0.3
  end_access %i0.3
  %i0.5: &Int = access [let] %i0.1
  %i0.6: &Int = access [let] %b0#0
  %i0.8: &Bool = access [set] %i0.0
  call @FunctionDecl(250806272)(%i0.6, %i0.5) to %i0.8
  end_access %i0.6
  end_access %i0.5
  end_access %i0.8
  %i0.11: &i1 = subfield_view %i0.0, 0
  %i0.12: &i1 = access [sink] %i0.11
  %i0.13: i1 = load %i0.12
  end_access %i0.12
  mark_state deinitialized %i0.1
  dealloc_stack %i0.1
  mark_state deinitialized %i0.0
  dealloc_stack %i0.0
  cond_branch %i0.13, b2, b1
b1():
  %i1.0: &Int = alloc_stack Int
  %i1.1: &Int = alloc_stack Int
  %i1.2: &Int = alloc_stack Int
  %i1.3: &word = subfield_view %i1.2, 0
  %i1.4: &word = access [set] %i1.3
  store i64(0x1), %i1.4
  end_access %i1.4
  %i1.6: &Int = access [let] %i1.2
  %i1.7: &Int = access [let] %b0#0
  %i1.9: &Int = access [set] %i1.1
  call @FunctionDecl(256638976)(%i1.7, %i1.6) to %i1.9
  end_access %i1.7
  end_access %i1.6
  end_access %i1.9
  %i1.12: &Int = access [let] %i1.1
  %i1.13: &Int = access [set] %i1.0
  call @FunctionDecl(1245186)(%i1.12) to %i1.13
  end_access %i1.12
  end_access %i1.13
  %i1.16: &Int = access [let] %i1.0
  %i1.17: &Int = access [let] %b0#0
  %i1.19: &Int = access [set] %b0#1
  call @FunctionDecl(259588096)(%i1.17, %i1.16) to %i1.19
  end_access %i1.17
  end_access %i1.16
  end_access %i1.19
  mark_state deinitialized %i1.2
  dealloc_stack %i1.2
  mark_state deinitialized %i1.1
  dealloc_stack %i1.1
  mark_state deinitialized %i1.0
  dealloc_stack %i1.0
  branch b3
b2():
  %i2.0: &word = subfield_view %b0#1, 0
  %i2.1: &word = access [set] %i2.0
  store i64(0x1), %i2.1
  end_access %i2.1
  branch b3
b3():
  return
}
```