<p>Types of Test Doubles</p>
<ul>
<li>Dummy</li>
<li>Stub</li>
<li>Spy</li>
<li>Mock</li>
<li>Fake</li>
<li>Service Virtualization</li>
</ul>

Note:
**Dummy**: A class that you pass into something when you don’t care how it’s used. e.g. As part of a test, when you must pass an argument, 
but you know the argument will never be used.
```
public class DummyAuthorizer implements Authorizer {
  public Boolean authorize(String username, String password) {
    return null;
  }
}
```

**Stub**: A class that returns a valid answer but always the same one.
```
public class AcceptingAuthorizerStub implements Authorizer {
  public Boolean authorize(String username, String password) {
    return true;
  }
}
```

**Spy**: You use a spy when you want to be sure that the authorize() method is called by the system.

Spy is basically partial mocking

**Mock**: A mock object is created to test the behavior of some other object
A car designer uses a crash test dummy to simulate the dynamic behavior of a human in vehicle impacts

Mock objects have the same interface as the real objects they mimic
Allow a client object to remain unaware of whether it is using a real object or a mock object.

A true mock is a mock that knows how to verify itself. 

**Fake**: You can drive a fake to behave in different ways by giving it different data. 
They are usually used for integration testing to simulate other parts of your system.

An object with limited capabilities (for the purposes of testing), e.g. a fake web service, or an in memory database

Fake objects actually have working implementations, but usually take some shortcut which makes them not suitable for production

**Service Virtualization**: It is the practice of creating virtual services and sharing them between developers and 
testers within a team and across teams. 

