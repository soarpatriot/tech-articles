###Test Doubles

##### 1. Dummy

##### 2. Stub(method) 

```
when(stationsService.getProvinces()).thenReturn(new ArrayList<>());
```

##### 3. Mock   ---  Mock objects have expectations; a test expects a value from a mock object, and during execution, a mock object returns the expected result. Also, mock objects can keep track of the invocation count, that is, the number of times a method on a mock object is invoked.

```
@Mock
StationsService stationsService;
```

##### 4. Fake ---   Fake objects are working implementations; mostly, the fake class extends the original class, but it usually hacks the performance, which makes it unsuitable for production. 

```
public class FakeAddressDao extends AddressDao{
@Override
  public SimpleJdbcTemplate getSimpleJdbcTemplate() {
    return jdbcTemplate;
} }
```

##### 5. Spy  ---  Spy is a variation of a mock/stub, but instead of only setting expectations, spy records the calls made to the collaborator. 

```
interface Printer{
    public void print(Object document,Object settings);
}

class SpyPrinter implements Printer{
  private int noOfTimescalled = 0;
   @Override
  public void print(Object document, Object settings) {
    noOfTimescalled++;
  }
  public int getInvocationCount() {
    return noOfTimescalled;
  }
}
```

