# Scealextric
A knowledge-based system for generating plots and rendering them as idiomatic English texts

Created by Tony Veale for use by the CC community. No warranty is offered or implied. Whe publishing work based in whole or in part on these resources, please cite the following paper as a reference for the Scéalextric approach and knowledge resource:

Veale, T. (2016). A Rap on the Knuckles and a Twist in the Tale: From Tweeting Affective Metaphors to Generating Stories with a Moral. In Proceedings of the AAAI Spring Symposium on Ethical and Moral Considerations in Non-Human Agents. 

Scéalextric:

We often think of stories in terms of journeys and paths. Indeed, the classic metaphors for taking about plots are fundamentally path-based, so we talk of dramatic "twists" and unexpected "turns" in a story. Some stories are explicitly about journeys, and are often filmed as road movies (like Easy Rider andDances with Wolves). Quest-based stories involving a search (for a ring, the holy grail, etc.) are also explicitly about the path from start to end.

Children love to play with train sets that allow them to build their own narrative microcosms and to imagine new stories within these toy worlds. They also love to play with dolls and action figures and combine them in new scenarios undreamt of by the toy manufacturers. Train sets, and their race-car equivalents (the most famous being Scalextric) allow kids to build complex tracks on which to run their train sets or race cars. The more complex the track, the greater the potential for narrative complexity and drama. Imagine if we (and our machines) could build stories as easily as children build train tracks and race tracks, from the same kinds of prefabricated track segments that simply click together end-to-end.

We call this approach to story-telling the Scéalextric approach, where "Scéal" is the Irish word for story and Scalextric is the most famous brand of track-based car-race simulator. A snapshot of a Scalextric track is shown above. Our "plot tracks" are not composed of plastic and metal but of actions and actors. More concretely, we represent each plot piece as a triple of actions. Here is an example of an action triple:

attack   are_defeated_by   bow_down_to

This triple should be read as follows:

A attack B   then   B defeat A    then   A bow_down_to B

Notice that the implied A (the protagonist) and B (the antagonist) turn each action into a semantic triple. So an action triple is actually a triple comprising three actions which are themselves a trio of semantic elements.
So this action triple (attack:are_defeated_by:bow_down_to) can be linked to others to build a longer plot, just as Scalextric track segments can be clicked together in an interlocking fashion to make a complete track. One might ask: what drives A to attack B? And what happens after a defeated A bows down to B?
To answer the first question we can connect a triple that ends with A attacking B, such as:

confide_in    are_betrayed_by    attack
which is a compact way of expressing this:

A confide_in B   then   B betray A   then   A attack B

As to the second question, we might connect the following triple to the end of our first triple. Notice how this triple starts with the same action that ends our first triple:

bow_down_to   are_commanded_by   kill_for

We can now connect these three triples end-to-end, with the end of one triple overlapping with the start of the next, to get the following three-act (7 action) sequence:

A confide_in B  then  B betray A  then  A attack B then  B defeat A  then  A bow_down_to B  then  B command A  then  A kill_for B

Each action in the sequence naturally leads in to the next. Yet not without twists and turns. It is unexpected (to A at least) that B betrays A when A confides in B. So we should render this "turn" at the surface level with the logical connective "but". When B commands an utterly defeated A, it is not surprising that A now does terrible things for B, so the connection between are_commanded_by and kill_for is more accurately rendered as "so" than "but". We can also capture this knowledge with a triple such as the following:

confide_in  but  are_betrayed_by

and

are_commanded_by  so   kill_for

The Scéalextric system contains a wealth of semantic triples: thousands of action triples, and thousands of connecting triples such as the above. It also contains idiomatic renderings for the actions in its action triples. For instance, if A attacks B then we can render this in idiomatic English as follows:

A attacked B with all its strength
A launched a massive attack on B
A pounced on B
A threw itself into an attack on B
A launched a full-frontal attack on B

What makes a good action to start a story? Using this track-building approach then any action can start a story if it is the starting action in an action triple. But this can appear abrupt: why, for instance, would A confide in B? It is useful to preface a story with a bit of background context to motivate the opening action. So we use a book of opening bookends that provides a scene-setting preamble for every possible opening action. For instance, the opening preamble for A confide_in B is:

B seemed an ideal confidante: open-minded and tight-lipped

Likewise, if a story ends on a specific action such as A kill_for B then we might add one of the following sentences as an epilogue:

thereafter A's soul belonged entirely to B and it would never again belong to its rightful owner
thereafter A treated B as its personal assassin and degraded it accordingly

By now it should go without saying that all of this information is also stored as a collection of triples. 
In fact, every useful piece of information in Scéalextric is stored as a semantic triple. 
Now, one can use XML, RDF, RDFS or OWL to store a collection of semantic triples, but the core of the triple stays the same regardless of the formalism we use to encode it. 
So why bother with a complex syntactic sugar for the sake of formalistic appearances? When it comes to maintaining and editing and sharing a large body of semantic triples the most flexible format is a spreadsheet. 
As mundane as it may sound, a spreadsheet is perfect for this kind of representation work. 
Every cell, representing as it does a value-containing intersection of a named column and a named row, represents a single triple. We can share spreadsheets easily (and post them on the Web as Google docs for communal editing) and cut-and-paste relevant parts with abandon. 
So every piece of information in Scéalextricis to be found in a spreadsheet. Each sheet can be saved as a tab-separated-values text file for easy processing by Java and Python programs, and we encourage you to add new columns and rows to each one, and to create new spreadsheets of your own with complementary forms of knowledge.
