# John Miller's CS-499 CS Capstone GitHub Pages Homepage

## Links

Artifact: [WeightTracker (Android Application)](https://github.com/JohnMiller-0/CS-360)

Enhancements: [FitGlitch (MEAN-Stack Web Application)](https://github.com/JohnMiller-0/FitGlitch)

Launched Capstone Project: <a href="https://fit-glitch.vercel.app" target="_blank" rel="noopener noreferrer">Visit FitGlitch</a>
  
## Video Code Review  
  
This is a video code review of the CS-360 WeightTracker Android application. The review highlights areas where the code succeeds and falls short, and then outlines my enhancement plans aligned with the course proficiencies and outcomes.  
  
<iframe width="560" height="315" src="https://www.youtube.com/embed/MBhkFcvRc2k?si=tAG2bHHe8T8NpVDt" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  
## Narratives  
  
### Artifact Justification  
  
&nbsp;&nbsp;&nbsp;&nbsp;The artifact I am enhancing is an Android application originally developed in 2024 for CS-360: Mobile Architecture and Programming, titled WeightTracker. The app allowed users to log their weight locally using SQLite. For the capstone project, I’m evolving this into a full-stack MEAN web application called FitGlitch. This transition highlights key areas of growth across Software Design and Engineering, Algorithms and Data Structures, and Databases. By replacing SQLite with MongoDB Atlas, I’ve restructured the backend to support multi-user access, secure data scoping via JWTs, and scalable schema-based storage. The frontend is rebuilt in Angular, introducing modular components for weight, meal, and workout tracking. These enhancements not only demonstrate an understanding of secure full-stack architecture but also reflect real-world practices like API-driven development, cloud integration, and client-server separation. Using the same artifact across my milestones allows me to deliver a cohesive, evolving solution that demonstrates growth in both technical ability and software design maturity.

  
### Software and Design

  
&nbsp;&nbsp;&nbsp;&nbsp;I have chosen to develop a full-stack application because it allows me to showcase all of the course competencies within a single, cohesive project. I can illustrate software design elements by creating a clean Model-View-Controller architecture. By demonstrating a clear Separation of Concerns (SoC), I reveal my ability to deconstruct business needs and technical problems into modular components and solutions. This approach is considered an industry best practice, as it promotes modularity, maintainability, and scalability in software systems (GeeksforGeeks, 2024). I have also implemented secure authentication and authorization strategies, including the use of the bcrypt library to generate strong password hashes and salts, as well as express-jwt for managing JSON Web Token (JWT)-based authentication. These tools help ensure that user data is protected and that only authorized users can access sensitive endpoints within the application.

&nbsp;&nbsp;&nbsp;&nbsp;I have managed to hit my planned course outcomes with my work on FitGlitch thus far. I have employed strategies for building collaborative environments by demonstrating a clear organization and SoC within my file hierarchy. I am using GitHub version control, which allows authorized users to contribute to and observe the codebase as it evolves, which reflects transparency and collaboration standards.

&nbsp;&nbsp;&nbsp;&nbsp;The lack of comments and documentation in my original WeightTracker application made the code review process more challenging than expected. Learning from that experience, I committed to improving the clarity and professionalism of my communication in the FitGlitch project. This growth is demonstrated through my video code review, the use of JSDoc for inline comments and file headers, and the visual aids I created to support the backend architecture and functionality.

&nbsp;&nbsp;&nbsp;&nbsp;I am using well-founded innovative tools, techniques, and skills within computer science practices to design and develop FitGlitch. The MEAN stack is a robust open-source framework, making it a popular choice for many developers (Bennett, 2023). I am also integrating well-known libraries such as JWT and bcrypt for authorization and authentication purposes, respectively.

&nbsp;&nbsp;&nbsp;&nbsp;Security should never be treated as an afterthought; instead, software must be developed using a Secure Software Development Lifecycle (SSDLC) approach from the outset. It is best practice to assess and implement security measures at every stage of development (New York State Office of Information Technology Services, 2024). The FitGlitch application is being developed with a security-first mindset to protect user data and ensure privacy. The Express API uses JWT middleware to secure protected routes and handle HTTP requests safely, while user passwords are securely hashed and never stored in plain text.

&nbsp;&nbsp;&nbsp;&nbsp;During the enhancement process, I developed several valuable technical skills and troubleshooting strategies. One key technique was using console logs and meaningful error messages to monitor application behavior and identify bugs during runtime. For example, while testing the getWeights function, I encountered an error retrieving data from the database, even though Visual Studio Code showed no syntax errors. After logging the incoming request object, I discovered that I was using a deprecated property (req.payload) instead of the updated req.auth. This experience reinforced the importance of runtime debugging and keeping up to date with evolving libraries and frameworks.


  
### Data Structures and Algorithms  
  
&nbsp;&nbsp;&nbsp;&nbsp;Unlike the original app, FitGlitch includes three distinct tracking categories—Weights, Workouts, and Meals—enabling users to monitor both long-term goals, such as weight loss or gain, and short-term goals through a daily caloric tracker.

&nbsp;&nbsp;&nbsp;&nbsp;I chose to continue developing this full-stack web application because it allows me to apply algorithmic principles and data structure strategies while building upon a cohesive, evolving project. The expanded scope of FitGlitch supports more advanced data transformations and business logic. For example, the FitGlitch API includes a route that uses a MongoDB aggregation pipeline to calculate the total calories consumed from meals and burned through workouts. These values are then processed using a JavaScript Map, allowing efficient iteration and matching to generate a structured JSON response. This response includes total calories in, calories out, net calories, and the difference between the net total and the user’s daily caloric goal.

&nbsp;&nbsp;&nbsp;&nbsp;The focus of this enhancement, alongside continuing my work from Enhancement One, has been to demonstrate my ability to design and evaluate computing solutions that address real-world problems using algorithmic principles and computer science practices and standards, while also managing the trade-offs inherent in design decisions. FitGlitch calculates net calories by aggregating calorie intake from meals and calories burned through workouts for each day within a specified range. This functionality is a direct result of thoughtful architectural decisions.

&nbsp;&nbsp;&nbsp;&nbsp;Using a JavaScript Map enabled efficient data transformation and lookup. JavaScript maps offer an average time complexity of O(1), meaning that each operation takes roughly constant time, regardless of the input size (GeeksforGeeks, 2023). This is ideal for handling the variable-length list of daily calorie totals returned by the aggregation pipeline.

&nbsp;&nbsp;&nbsp;&nbsp;The MongoDB aggregation pipeline allows me to work with large datasets by performing grouping and calculations directly within the database query. This significantly reduces the load on the Node.js server and limits the amount of data that needs to be transferred. Aggregation pipelines are widely considered efficient and reliable for these reasons (Aram, 2024).

&nbsp;&nbsp;&nbsp;&nbsp;Designing and building this enhancement has allowed me to learn and apply several new techniques. This was my first time integrating a MongoDB pipeline into an application, and the troubleshooting process was challenging. I eventually found the solution in the Mongoose.js documentation: when constructing queries, Mongoose automatically coerces strings into the appropriate data types that MongoDB expects. For example, if MongoDB expects a number and a string representation of a number is passed, Mongoose will cast it. However, this coercion does not apply to aggregation pipelines. As a result, passing a userId as a string rather than an ObjectId led to empty query results, even when everything else in the pipeline was correct.


  
### Databases  
  
&nbsp;&nbsp;&nbsp;&nbsp;I selected this artifact for the databases category because the FitGlitch web application demonstrates secure, scalable integration with a cloud-hosted database. In the enhanced version, MongoDB Atlas replaces the original local SQLite storage, enabling a multi-user architecture. Each entry in the Weight, Meal, and Workout collections includes a userId field that ties the data to the authenticated user. This ID is extracted from a JWT, and all queries are filtered using middleware to ensure that only the appropriate user’s data is returned or modified. This implementation adheres to industry-standard practices for database-driven web applications, demonstrating expertise in schema design, query filtering, secure data access, and cloud database integration.

&nbsp;&nbsp;&nbsp;&nbsp;My work integrating MongoDB, first in a local instance and later a cloud-based version using MongoDB Atlas, has allowed me to demonstrate mastery of several course outcomes. Integrating a cloud-hosted version of the database fosters collaboration by allowing remote work on FitGlitch. Now, instead of reporting changes on local machines, API functionality may be observed in real-time in a live environment.

&nbsp;&nbsp;&nbsp;&nbsp;I have delivered professional-quality communication through detailed code comments, structured headers, and well-maintained documentation. The Mongoose schemas in the FitGlitch backend are written with explicit value types and required fields, making the data structure easy to understand for other developers. Additionally, I designed an API endpoint table that documents all routes, HTTP methods, expected inputs, and database interactions. This allows developers unfamiliar with the codebase to contribute.

&nbsp;&nbsp;&nbsp;&nbsp;Integrating with a cloud instance demonstrates the ability to utilize well-founded and innovative techniques, skills, and tools in computing practices to implement computer solutions that deliver value and achieve industry-specific goals. Cloud computing is a well-established field that is currently underserved (Flexera, 2025). Thus, this demonstration is career-relevant.

&nbsp;&nbsp;&nbsp;&nbsp;A security mindset is demonstrated by ensuring that all data is properly scoped to the userId field. The userId is parsed from the encrypted JWT via middleware, so it’s never exposed to the user or passed through the frontend. It’s used alongside the token’s signature for authorization, meaning users can only access or modify entries in the weight, workout, and meal collections that belong to them. This setup helps secure the database and prevents cross-user data leaks, which is crucial in any multi-user application handling personal information. Using a hashing service, such as bcrypt, to hash the user’s password before submitting it to the database is also a best practice, which FitGlitch successfully implements (Percona, 2023).   





### References

Aram, C. (2024, February 25). MongoDB aggregation pipelines vs traditional queries with find. Medium. https://zerofilter.medium.com/mongodb-aggregation-pipelines-vs-&nbsp;&nbsp;&nbsp;&nbsp;traditional-queries-with-find-c95f372257aa

Bennett, J. (2023, December 15). Are MERN and MEAN stack still in demand for web development in 2024? Medium. https://medium.com/@jessicajournal/are-mern-and-mean-stack-&nbsp;&nbsp;&nbsp;&nbsp;still-in-demand-for-web-development-in-2024-9c56a7314ad6

Conboy, S. (2023, July 9). When to use a Map instead of an Object in JavaScript. Medium. https://medium.com/@conboys111/when-to-use-a-map-instead-of-an-object-in-&nbsp;&nbsp;&nbsp;&nbsp;javascript-e396f1b27b19

Flexera. (2025, March 19). 2025 State of the Cloud report. Flexera. https://info.flexera.com/CM-REPORT-State-of-the-Cloud

GeeksforGeeks. (2021, October 31). Documentation comments in JSDoc. https://www.geeksforgeeks.org/documentation-comments-in-jsdoc/

GeeksforGeeks. (2023, June 8). Internal working of Map in JavaScript. https://www.geeksforgeeks.org/internal-working-of-map-in-javascript/

GeeksforGeeks. (2024, February 13). Separation of concerns (SoC). https://www.geeksforgeeks.org/separation-of-concerns-soc/

Mongoose.js. (n.d.). Mongoose v8.0.3: Aggregation. https://mongoosejs.com/docs/api/aggregate.html

New York State Office of Information Technology Services. (2024, May 9). Secure System Development Life Cycle Standard (NYS-S13-001). https://its.ny.gov/secure-system-&nbsp;&nbsp;&nbsp;&nbsp;development-life-cycle-standard

Percona. (2023, November 9). Securing your MongoDB database: Essential best practices. https://www.percona.com/blog/securing-your-mongodb-database-essential-best-&nbsp;&nbsp;&nbsp;&nbsp;practices/






