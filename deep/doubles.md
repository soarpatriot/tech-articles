###Test Doubles 测试替代
1. Dummy
2. Stub(method) 
3. Mock   ---  Mock objects have expectations; a test expects a value from a mock object, and during execution, a mock object returns the expected result. Also, mock objects can keep track of the invocation count, that is, the number of times a method on a mock object is invoked.
4. Fake ---   Fake objects are working implementations; mostly, the fake class extends the original class, but it usually hacks the performance, which makes it unsuitable for production. 
5. Spy  ---  Spy is a variation of a mock/stub, but instead of only setting expectations, spy records the calls made to the collaborator. 


