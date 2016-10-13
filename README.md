# hello-world
##**Ideas for a Relational Expert System (RES) - copyright 1992 Vince Ladewig**
The initial idea grew from a desire to create an expert system shell back in 1992 for use in building a expert system for determining the "site of lesion" from information obtained from performing an audiometric battery of tests:  
  + PTA - air and bone  
  + Tympanometry  
  + Impedance  
  + Reflex  
  + Speech  
  + Auditory Brainstem Evoked Responses (ABER)  
  
##**The RES as first developed**
  A problem might be a main problem or a subproblem  
  A problem has inputs which take on allowed values    
  A problem space is the table generated from all combinations of values of all inputs for a problem  
  A problem has results  
  A result might be an answer or flow into another problem  
  Each row in the generated problem space table is assigned a result by the expert  
  Various checks are made to ensure integrity of the problems and problem spaces  
  A mechanism exists for traversing the web of problems  
  During the traverse a record is kept of the problem spaces visited, the values of inputs used and the results obtained  
  An input might be the result from a problem  
  The RES allows for backward chaining - the depth was determined by the amount of memory  
  A traverse of a problem web is captured in a log  
  The RES allows for refining the granularity of the web of problems  

##**Some History**
The initial published RES system (Version 2.0MU circa 1992) was built in DOS using a product called DataBoss (Kedwell Software - Brisbane OZ based).  
DataBoss was a flexible development environment which used TurboPascal (Borland) as the language for building relational database management systems.  
DataBoss provided the generic code for managing the housekeeping (add, edit, delete etc) after the developer entered the table definitions, keys and uniqueness constraints as well as field types and constraints.  
DataBoss allowed the developer to insert TurboPascal code into the "skeleton" files used by DataBoss to generate the source code for each user defined data base.
The generated source code was then compiled.  

##**Present Plan**
The present plan (October 2016) is to revist the initial definitions (NIAM entity relationship model) upon which the RES is based and use these ideas to develop a graphic interface using "R" and the "igraph" package.  
mySQL may be the initial database used for defing the updated RES which is then read to build the web of problems.  
It is likely that initially an expert system suitable for testing the ideas in R may need to be bootstrapped from predefined tables (data frames) built by hand to reflect what would available from reading a RES built in mySQL.    
