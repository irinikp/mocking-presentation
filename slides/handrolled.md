Why not stop at hand-rolled fakes?

Note:
Any developer could manually make a fake class

The simple fake class created yesterday, becomes a maintenance nightmare today.

Nightmare reasons:

New methods are added intertwining with the existing object -> you need to implement them on the fake one. 
Extra work without actual value.
As the functionality of the fake object grows, more maintenance is needed, maybe even its own unit tests!

Your manual fake object could accidentally perform real actions.

