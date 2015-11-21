
#How can we do it in java?

Unit test framework in java

1. SpryTest 
2. Jtest 
3. Junit 
4. TestNG

First JUnit test
```
asssertTrue  assertFalse   assertNull assertNotNull assertEquals assertSame assertNotSame  
```
```
assertThat(calculatedTax, is(not(thirtyPercent)) ); 
assertThat(phdStudentList, hasItem(DrJohn) ); 
assertThat(manchesterUnitedClub, both( is(EPL_Champion)).and(is(UEFA_Champions_League_Champion)) ); 

```
```
@BeforeClass @AfertClass @Before @After
```
```
@Test(expected=RuntimeException.class) 
@Test(timeout=10) @RunWith(Theories.class)    @Rule     @Category 
```
```
@RunWith 
@RunWith(Suite.class) 

@RunWith(Parameterized.class) 
```

Remove you System.out.println

