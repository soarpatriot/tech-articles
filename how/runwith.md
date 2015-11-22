###Runwith

#####When a class is annotated with @RunWith or the class extends a class annotated with @RunWith, JUnit will invoke the class that it references to run the tests on that class, instead of using the built-in runner. The @RunWith annotation is used to change the nature of the test class.

#####@RunWith

#####@RunWith(Suite.class) 

```
import org.junit.runner.RunWith;
import org.junit.runners.Suite;

/**
 * Created by liuhaibao on 15/11/22.
 */
@RunWith(Suite.class)
@Suite.SuiteClasses({ AssertThatTest.class,
        SanityTest.class,ExceptionTest.class })
public class DemoSuite {
}

```

#####@RunWith(Parameterized.class)

Parameterized tests are used for multiple iterations over a single input to stress the object in test. The primary reason is to reduce the amount of test code.

```
public class Factorial {

    public long factorial(long number) {
        if(number == 0) {
            return 1;
        }
        return number*factorial(number-1);
    }
}
```
```
package com.xiaojiuwo.demo;

import com.xiaojiuwo.utils.Factorial;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;

import java.util.Arrays;
import java.util.Collection;

import static org.junit.Assert.assertEquals;

/**
 * Created by liuhaibao on 15/11/22.
 */
@RunWith(Parameterized.class)
public class ParameterizedFactorialTest {

    @Parameterized.Parameter(value=0)
    public int number;
    @Parameterized.Parameter(value=1)
    public int expectedResult;

    @Test
    public void factorial() throws Exception {
        Factorial fact = new Factorial();
        assertEquals(fact.factorial(number),expectedResult);
    }
    @Parameterized.Parameters
    public static Collection<Object[]> factorialData() {
        return Arrays.asList(new Object[][]{
                {0, 1}, {1, 1}, {2, 2}, {3, 6}, {4, 24}, {5, 120}, {
                6, 720}
        });
    }
}
```


#####@RunWith(Theories.class)    
JUnit theories are an alternative to JUnit’s parameterized tests. A JUnit theory encapsulates the tester’s understanding of an object’s universal behavior. This means whatever a theory asserts is expected to be true for all data sets. Theories are useful for finding bugs in boundary-value cases.

```
package com.xiaojiuwo.demo;

import org.junit.experimental.theories.DataPoint;
import org.junit.experimental.theories.Theories;
import org.junit.experimental.theories.Theory;
import org.junit.runner.RunWith;

/**
 * Created by liuhaibao on 15/11/22.
 */
@RunWith(Theories.class)
public class TheoryTest {
    @DataPoint public static String jack ="human";
    @DataPoint
    public static String mike ="Mike";
    @Theory
    public void theory_test(String firstName, String lastName) {
        System.out.println("Sanity check "+firstName+", "+lastName);
    }
}

```

#####@Rule     
Rules allow very flexible addition or redefinition of the behavior of each test method in a test class. Rules are like Aspect Oriented Programming (AOP); we can do useful things before and/or after the actual test execution.

```
package com.xiaojiuwo.demo;

import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.Timeout;

/**
 * Created by liuhaibao on 15/11/22.
 */
public class RuleTest {
    @Rule
    public Timeout globalTimeout =  new Timeout(20);
    @Test
    public void testInfiniteLoop1() throws InterruptedException{
        Thread.sleep(1);
    }
    @Test
    public void testInfiniteLoop2() throws InterruptedException{
        Thread.sleep(30);
    }
}

```

#####@Category 
Categories is a kind of Suite
create SimpleTest interface and ComplexTest
```
package com.xiaojiuwo.demo;

import org.junit.Test;
import org.junit.experimental.categories.Category;

/**
 * Created by liuhaibao on 15/11/22.
 */
@Category({SimpleTests.class, ComplexTest.class})
public class OtherTest {
    @Test
    public void c() {
    }
}



package com.xiaojiuwo.demo;

import org.junit.Test;
import org.junit.experimental.categories.Category;

import static org.junit.Assert.fail;

/**
 * Created by liuhaibao on 15/11/22.
 */
public class SomeTest {
    @Test
    public void a() {
        fail();
    }
    @Category(SimpleTests.class)
    @Test
    public void b() {
    }
}



package com.xiaojiuwo.demo;

/**
 * Created by liuhaibao on 15/11/22.
 */

import org.junit.Test;
import org.junit.experimental.categories.Categories;
import org.junit.runner.RunWith;
import org.junit.runners.Suite;

@RunWith(Categories.class)
@Categories.IncludeCategory(SimpleTests.class)
@Suite.SuiteClasses( { SomeTest.class, OtherTest.class }) // Note that Categoriesis a kind of Suite
public class SimpleSuiteTest {

}


```
