
###Exceptions test

#####Time out
@Test(timeout=10)  millisecond
```
package com.xiaojiuwo.demo;

import org.junit.Test;

/**
 * Created by liuhaibao on 15/11/22.
 */
public class TimeOutTest {
    @Test(timeout=2000)
    public void sleep_3_seconds() throws Exception {
        Thread.sleep(3000);
    }
}

```
#####RuntimeException
@Test(expected=RuntimeException.class) 
```
@Test(expected=RuntimeException.class)
public void exception() {
    throw new RuntimeException();
}
```
