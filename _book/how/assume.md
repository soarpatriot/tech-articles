###Assume
Before executing a test, we can check our assumption using the assumeXXX methods. If our assumption fails, then the assumeXXX methods throw AssumptionViolatedException, and the JUnit runner ignores the tests with failing assumptions.

```
import org.junit.Test;

import static org.junit.Assert.assertFalse;
import static org.junit.Assume.assumeTrue;

/**
 * Created by liuhaibao on 15/11/22.
 */
public class Assumption {

    boolean running = false;

    @Test
    public void test_when_running() throws Exception{
        boolean aa = true;
        assumeTrue(running);
        assertFalse(aa);
    }
}

```
