
###Setups

#####Do something before or after a test or class

* @BeforeClass 
* @AfertClass 
* @Before 
* @After

```
import org.junit.After;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Test;
public class SanityTest {
     @BeforeClass
     public static void beforeClass() {
       System.out.println("***Before Class is invoked");
     }
     @Before
     public void before() {
       System.out.println("____________________");
       System.out.println("\t Before is invoked");
     }
     @After
     public void after() {
       System.out.println("\t After is invoked");
       System.out.println("=================");
     }
     @Test
     public void someTest() {
       System.out.println("\t\t someTest is invoked");
     }
     @Test
     public void someTest2() {
       System.out.println("\t\t someTest2 is invoked");
     }
    @AfterClass
      public static void afterClass() {
        System.out.println("***After Class is invoked");
    } 
}
```

#####Ignore a test

Just add @Ignore on a method

```
public class Assumption {

    boolean running = false;

    @Ignore 
    @Test
    public void test_when_running() throws Exception{
        boolean aa = true;
        assumeTrue(running);
        assertFalse(aa);
    }
}
```
