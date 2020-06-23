
Solid Design Principle: 

SRP : 
Single responsibility for methods as well as class.

Open Close: 
Code should be open for expansion and close for modification. 

Liskov Substitution:  
A sub type should be replaceable for base type. Design and interface in a way that up-casting will not break anything. 

Interface Segregation: 
The interface should not do too much, follow SRP for interfaces. 

Dependency Inversion
High level module should not depend on low level module, suppose a high level module access a member var of low level module directly say it’s a vector and iterate over it, what if the low level module owner will changes it to map?
 
Builder:
Building objects in pieces.

Factory:
Building object in wholesale. 

Adapter:
Adapting to an interface, like a square can behave as a rectangle. Adapt square to behave as rectangle. 
Hoe to: Create new adapter class like SquareToRechagle, pass square in ctor, check for copies your adapter is creating.

Prototype:
Create a small proto and pass/copy it to all new objects. Create a static const proto for once.

Bridge:
Decouple hierarchies, It's like we have Shape -> Square, Rect, Circle and we have different renders like Raster, Vector etc. It will become n*m in normal case. 
Create interface for both of them and compose renderer interface ref or object in shape and call the appropriate method from that specific shape.

Composite: 
Treat all objects(scalar or non scalar) same. In case we have a common object for a simple concrete type and a complex concrete class. We can should treat them equally.

Decorator: 
Alter/add behavior without altering object.

Facade: 
Provide High level API’s to facilitate over a set of classes, or wrap some piece of code in main in a class.


Flyweight: 
Space optimization when we have data redundancy. 
Ex: Use with similar name and surname. Store name surname in tables and maintain pointers somewhere. 

Proxy: 
Same interfaces underlying functionality, different behavior. 
To create proxy, replicate existing interface and add functionality.
Class act as interface to a resource(local, remote, easy to construct or complex creation) like smart pointers

Property Proxy →  Wrapper over primitives type
Virtual proxy → Sometime we come up with a scenario where we get some information in constructor and we have to call a virtual method at some other part to process the same information. 

Ex: 
BitMap class receiving filename in ctor, sit loads the bitmap by using filename and store it as class state and later a draw method will be called to use the file name to draw bitmap. 
In case we are not allowed to change the Bitmap class, we should have a proxy class which may have a Bitmap pointer, it may receive filename in ctor and in virtual method it may create object and call draw on pointer

Chain Of Responsibility: 
Component tied together and then we choose the next one from base class.

Command
Encapsulate all operation in object. 
Process commands to subject.
Can create composite commands.

Command → Ask for an action, no return
Query → No action, only return value

Interpreter:  
Parse and process data.

Iterator: 
Class object support traversal, mostly by adding begin(), end()

Mediator: 
Facilitate communication b/w components. Ex: Players in online games, can come and go any time. 
Component add without knowing each other.
Create Mediator, inject mediator to each component.
Mediator have function which component can call. 
Component list themselves for being notified. 
Mediator notify them by iteration over the list.

Strategy (Policy Based Design)
Define partial and use it later to refine later.
Enable behavior to be selected later, run time or compile time.

Template Method: 
Skeleton in base class, implementation in der classes
High level Blue print for algorithm to be used for inheritors. 


FAQ’s:
What is difference between proxy and adapter?

If you need to adapt to some interface provided for you, use an adapter. If you need to enhance an object's functionality while not changing its interface, use a proxy.

What is difference between proxy and decorator?
Proxy use identical interface, decorator gives enhanced interface. 
Decorator holds ref to object being decorated, proxy does not.

Strategy vs Template: 
Strategy uses composition. 
Template method used inheritance. 
