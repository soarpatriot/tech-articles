
###Assert types

```
asssertTrue  
assertFalse   
assertNull 
assertNotNull 
assertEquals 
assertSame 
assertNotSame  
```

###A few utility methods of CoreMatchers are:
```
allOf, anyOf, both, either, 
describedAs, everyItem, 
is, isA, 
anything, 
hasItem, hasItems, 
equalTo, any, 
instanceOf, not, nullValue, notNullValue, 
sameInstance, theInstance ,
startsWith, endsWith, and containsString. 
```

###Assert that example
```
assertThat(calculatedTax, is(not(thirtyPercent)) ); 
assertThat(phdStudentList, hasItem(DrJohn) ); 
assertThat(manchesterUnitedClub, both( is(EPL_Champion)).and(is(UEFA_Champions_League_Champion)) ); 
```

###Example

```
import static org.hamcrest.CoreMatchers.not;
import static org.hamcrest.CoreMatchers.is;
import static org.junit.Assert.assertThat;
import org.junit.Test;
public class AssertThatTest {
  @Test
  public void verify_Matcher() throws Exception {
￼￼￼
    int age = 30;
    assertThat(age, equalTo(30));
    assertThat(age, is(30));
    assertThat(age, not(equalTo(33)));
    assertThat(age, is(not(33)));
  }
}
```
