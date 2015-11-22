###Rules

#####Rules allow very flexible addition or redefinition of the behavior of each test method in a test class. Rules are like Aspect Oriented Programming (AOP); we can do useful things before and/or after the actual test execution.

```
@Test(expected=RuntimeException.class) 
@Test(timeout=10)
```

