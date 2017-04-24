"Graph-Theory-GMIT-Timetable"
This project is a timetabling graph database for the Galway Mayo Institute of Technology which I was asked to do as part of my Graph Theory module in the said institute. To create our graph database, we were asked to use Neo4j. I will outline what nodes/relationships I will create and what information I will set as the nodes. As a starter for myself in this project I am going to create the database for my year only in the current semester (Year 3, Semester 2).

Nodes
I chose to set the following as the nodes of my database:
LecturerShows all lecturersGroupsShows all groups in 3rd yearRoomsShows all roomsModuleShows all modulesDayTimeShows the days and times of class
I decided that for what I wanted to achieve I would use these as my nodes. All data for the nodes are read in from csv files. I chose to store them in csv files thinking that in the future if someone, who could not understand databases and querying them to add more data, could simply go to the csv file they wish to add the information into and then the nodes would be created simply with one line of simple code.

Lecturers are my first set of nodes as any lecturer may teach one or more module to a single year of the same course. Having lecturers as their own node will make querying, in my mind, easier as you can search for the lecturer by their name and then all the relationships connected to the node. This in turn will show all modules taught by the lecturer and what times they are teaching, to who and in what room.

Every course is split into what we call “Lab Groups” to enable a more tutorial/practical based environment. This is what made me decide to set them groups are a node. Not all groups will have the exact same timetable so if the database is queried to show just one lab group, then it will be working as the timetable that I envision it should.

In an institute where there are a variety of different courses, from software to catering studies, not all courses need the same type of room. Setting the rooms to nodes will enable me to add a description of what type of room the class will be held in. I decided to do this because I am thinking of first year students who don’t understand the room numbers at the start. With the help of the nodes, the students will be able to see where the class is being held and will know what to bring (copy for lecture, laptop for lab times).

Modules are my next node as it will show clearly what the class is. Not all modules are specific to one course.

DayTime is my way of connecting the day and time in one module. I decided to do it this way for the first draft of the database. I populated the csv file by referring to my timetable and picking every class off the timetable and adding that slot as a node (eg Monday 10-11)

Relationships
The relationships I wish to create are as follows:

Lecturer – ModuleShows what the lecturer teaches each moduleLecturer – DayTimeShows the days and times the lecturer is teachingGroup – DayTimeShows what group is where at what timeModule – DayTimeShows which module is being taughtRoom – DayTimeShows what room at what time
In my opinion this would be the ideal way for me to set up the relationships between nodes. The lecturer – module node will be seen as the lecturer TEACHES the module, the lecturer will then be TEACHING_AT a said day/time, a group will be ATTENDS at a said day/time, a module will be TAUGHT_AT a said day/time and a room will be BOOKED at a said day/time.

Conclusion
Whilst making this graph database I realised that my methods weren’t going to work when I was making the relationship between the nodes. While it was simple to create, the nodes reading from csv files, I had troubles trying to do the same for the relationships. It was my goal to read them in from a csv file also but when I kept meeting problem after problem I decided it was best to hard code the information straight into Neo4j. When I was making the relationships, I couldn’t find a way to keep my nodes as is and then connect the groups to certain classes at certain times. Using a new platform like Neo4j has been very enjoyable. Yes, I did run into problems along the way and yes, parts are very repetitive but in saying that I would see myself using Neo4j as it is very usable and as far as my knowledge goes, it stores and shows data in very clear and concise format. 

References
1. http://timetable.gmit.ie/
2. https://neo4j.com/docs/
3. Problem sheets by Ian McLoughlin


