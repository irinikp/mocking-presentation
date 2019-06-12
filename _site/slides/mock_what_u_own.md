"Don't mock what you don't own"

Note:
A fake object helps us create the interface between the code we test and the code it depends on. 
It provides a safe, easy-to-change testbed. Because the thing we fake doesn't exist yet; so if it turns out to 
be awkward to specify the interaction, it is cheap to throw it away and re-try. So this phrase is used to determine 
that we write our tests to get a design feedback.

Now in the case where we feel the need to mock a third party we don't own, we can't control that it won't change down 
the line. So we can take all those API calls, the things that interact with something we don't own and we isolate them 
behind a class that we do own (a wrapper). Then we could even create our own API (something more readable to us) and 
call this an adapter. And now that we have something we do own, we can mock it however we need to. But at some point you 
still need to write an integration test that hits that API make sure that everything works as expected