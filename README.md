Sinon.JS Assertions for Chai
============================

**sinon-chai** provides a set of custom assertions for using the [Sinon.JS][sinon] spy, stub, and mocking framework
with the [Chai][chai] assertion library. You get all the benefits of Chai with all the powerful tools of Sinon.JS.

Instead of using Sinon.JS's assertions:

```javascript
sinon.assertCalledWith(mySpy, "foo");
```

or awkwardly trying to use Chai's `should` or `expect` interfaces on spy properties:

```javascript
mySpy.calledWith("foo").should.be.ok;
expect(mySpy.calledWith("foo")).to.be.ok;
```

you can say

```javascript
mySpy.should.have.been.calledWith("foo");
```


## Assertions

All of your favorite Sinon.JS assertions made their way into sinon-chai. We show the `should` syntax here; the `expect`
equivalent is also available.

<table>
    <tr>
        <th>Sinon.JS property/method</th>
        <th>sinon-chai assertion</th>
    </tr>
    <tr>
        <td>called</td>
        <td>spy.should.have.been.called</td>
    </tr>
    <tr>
        <td>calledOnce</td>
        <td>spy.should.have.been.calledOnce</td>
    </tr>
    <tr>
        <td>calledTwice</td>
        <td>spy.should.have.been.calledTwice</td>
    </tr>
    <tr>
        <td>calledThrice</td>
        <td>spy.should.have.been.calledThrice</td>
    </tr>
    <tr>
        <td>calledBefore</td>
        <td>spy1.should.have.been.calledBefore(spy2)</td>
    </tr>
    <tr>
        <td>calledAfter</td>
        <td>spy1.should.have.been.calledAfter(spy2)</td>
    </tr>
    <tr>
        <td>calledOn</td>
        <td>spy.should.have.been.calledOn(context)</td>
    </tr>
    <tr>
        <td>alwaysCalledOn</td>
        <td>spy.should.always.have.been.calledOn(context)</td>
    </tr>
    <tr>
        <td>calledWith</td>
        <td>spy.should.have.been.calledWith(...args)</td>
    </tr>
    <tr>
        <td>alwaysCalledWith</td>
        <td>spy.should.always.have.been.calledWith(...args)</td>
    </tr>
    <tr>
        <td>calledWithExactly</td>
        <td>spy.should.always.have.been.calledWithExactly(...args)</td>
    </tr>
    <tr>
        <td>alwaysCalledWithExactly</td>
        <td>spy.should.always.have.been.calledWithExactly(...args)</td>
    </tr>
    <tr>
        <td>returned</td>
        <td>spy.should.have.returned(returnVal)</td>
    </tr>
    <tr>
        <td>alwaysReturned</td>
        <td>spy.should.have.always.returned(returnVal)</td>
    </tr>
    <tr>
        <td>threw</td>
        <td>spy.should.have.thrown(errorObjOrErrorTypeStringOrNothing)</td>
    </tr>
    <tr>
        <td>alwaysThrew</td>
        <td>spy.should.have.always.thrown(errorObjOrErrorTypeStringOrNothing)</td>
    </tr>
</table>

For more information on the behavior of each assertion, see
[the documentation for the corresponding spy methods][spymethods]. These of course work on not only spies, but
individual spy calls, stubs, and mocks as well.


## Installation and Usage

Do an `npm install sinon-chai` to get up and running. Then:

```javascript
var chai = require("chai");
var sinonChai = require("sinon-chai");

chai.use(sinonChai);
```

You can of course put this code in a common test fixture file; for an example using [Mocha][mocha], see
[the sinon-chai tests themselves][fixturedemo].


[sinon]: http://sinonjs.org/
[chai]: http://chaijs.com/
[mocha]: http://visionmedia.github.com/mocha/
[fixturedemo]: https://github.com/domenic/sinon-chai/tree/master/test/
[spymethods]: http://sinonjs.org/docs/#spies-api
