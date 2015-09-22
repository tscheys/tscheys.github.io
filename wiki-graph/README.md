wiki-graph will try to visualize the link between wikipedia pages.
For example: when you are researching a dynasty of kings, a lot of times it is hard
to keep track of how all the kings are related. 

You will be able to see how one king relates to others. Ideally we will do this by
using a pedigree made in d3. 

Roadmap for MVP:
- get html page for certain king from api x
- get successor information through wikipedia api x
- display that information x
- make an api call to that succesor's page on wikipedia and display his information x
- make a function that will keep doing this 3 levels deep x
- print title of king and start and end year of reign x
- print link x
- users should be able to click a link to that monarch's page x
- make option input to select: successor, father, mother
- make presentation 

Bugs: 
- links point to wrong pages x
- flush visual div x

Main functionality: 
- Searches wikipedia for the king you requested
- Makes recursive ajax call to connected page 5 levels down 
- handles wikipedia disambiguation pages  
- uses d3 to render these boxes (next step would be to make some kind of grpah or tree to visualize multiple connections)
- you can link through successor, predecessor, mother and father
- gives you the link to the wikipedia page, some random information
- selects a random sentence from the page as a fun fact