###First JUnit test
```
public boolean isCreatedDateGt(Date boundary){
    return this.createdDate.getTime() > boundary.getTime()? true: false;
}
```
```
package com.xiaojiuwo.models;

import org.junit.Test;

import org.junit.Assert;
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;

/**
 * Created by liuhaibao on 15/10/25.
 */
public class UserTest {

    @Test
    public void isCreatedDateGt(){
        User user = new User();
        DateFormat df = new SimpleDateFormat("yyyy-MM-dd hh:mm");
        Date created, compared;
        try{
            created = df.parse("2011-05-26 15:23");
            compared = df.parse("2011-09-26 15:23");

            user.setCreatedDate(created);
            boolean result = user.isCreatedDateGt(compared);
            Assert.assertFalse("failure - should be true", result);
            //Assert.assertTrue(result);

        }catch (Exception e){
            Assert.fail("failure - should not be here");
            //Assert.fail();
        }
    }

    @Test
    public void isCreatedDateGtNot(){
        User user = new User();
        DateFormat df = new SimpleDateFormat("yyyy-MM-dd hh:mm");
        Date created, compared;
        try{
            created = df.parse("2011-10-26 15:23");
            compared = df.parse("2011-09-26 15:23");

            user.setCreatedDate(created);
            boolean result = user.isCreatedDateGt(compared);
            Assert.assertTrue("failure - should be true", result);
            //Assert.assertTrue(result);

        }catch (Exception e){
            Assert.fail("failure - should not be here");
            //Assert.fail();
        }
    }

}
```

