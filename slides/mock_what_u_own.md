"Don't mock what you don't own"

Note:
<u>A fake object helps us create the interface between the code we test and the code it depends on.</u>
It provides a safe, easy-to-change testbed. Because the thing we fake doesn't exist yet; so if it turns out to 
be awkward to specify the interaction, it is <u>cheap to throw it away and re-try</u>. So this phrase is used to <u>determine 
that we write our tests to get a design feedback</u>.

Now in the case where we feel the need to mock a third party we don't own, we can't control that it won't change down 
the line. So we can take all those API calls, the things that interact with something we don't own and we isolate them 
behind a class that we do own (a wrapper). Then we could even create our own API (something more readable to us) and 
call this an adapter. And now that we have something we do own, we can mock it however we need to. But at some point you 
still need to write an integration test that hits that API make sure that everything works as expected

For example, for anyone using Laravel, if you are familiar with Eloquent, this is an Active Record implementation that works
with your database. You can't mock Eloquent, if you absolutely need to mock it, then you should create a wrapper for that. 
