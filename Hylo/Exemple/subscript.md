# Code
```
extension UInt32 {
	public subscript(_ i: Int) -> Bool {
		sink { return ( self & (1 << i)) != 0 }
		let { yield self & (1 << i)) != 0 }
		inout {
			var b = self[i]
			yield &b
			if b { &self |= 1 << i }
			else { &self  &= ~(1<<i)}
		}
	}
}

public fun main(){
	var s: Uint = 0
	&s[4] = true
	print(s)
}
```

# IR
Ne compile pas