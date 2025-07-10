# Blog Post API
The Blog API Service is a backend micro service that can be integrate with any Content Management Department’s frontend portal. This is a core feature in any internal knowledge-sharing platform. This service expose endpoints to create, read, update, and delete blog posts, and manage authors.

## 🔭 Development Scope
This build:

🍃	A RESTful API using Java + Spring Boot 

🐘	PostgreSQL as the relational DB 

📮	Tested through Postman 

🐳	Fully containerized via Docker 

🙆🏽‍♂️    Following Agile practices 

🔄    full Software Development Lifecycle
      
 
# 📔 Phase 1: Requirements Gathering & Information Research (Sprint 1)
**Agile Methodologies** used:


•	**Face to face communication**. When gathering requirements, it is better to speak with a human instead of communicating through emails. 

•	**Working software over comprehensive documetation**. Would you rather have an application that FUNCTIONS correctly instead of having a large set of rules that are too confusing to follow for implementation?

•	**Individuals and interactions over process and tools**. It is a great practice to focus on the - "who is helping us with this?" Over "Does it work yet? Or not..... Creativity is the birth child of brainstorming by collaborating with collegues who may have different sources of knowledge and experience that can prove to be usefull throughout the process!

🥅 Functional Requirements
•	Users can:

•	Create a blog post

•	Read one or all blog posts

•	Update a blog post

•	Delete a blog post

•	Associate each blog post with an author

•	Optional: Add tags or categories

🥅 Non-Functional Requirements

•	Secure API endpoints (basic JWT later if needed)

•	Input validation and meaningful error messages

•	Logging using Spring Boot’s logger

•	Scalable architecture with Docker

•	API tested via Postman collections (Swagger API tester UI optional for collaboration purposes with front end developers)


# ⚜️ Phase 2: Plan and Design (Sprint 2)

🧱 System Design

Java Entities:

•	BlogPost (id, title, content, created_at, updated_at, author_id)

•	Author (id, name, email, bio)

📁 Project Structure


src/

 └── main/
 
     ├── java/com/example/blogapi/
     |
     
     │    ├── controller/
     |
     
     │    ├── model/
     |
     
     │    ├── repository/
     |
     
     │    ├── service/
     |
     
     │    └── BlogApiApplication.java
     |
     
     └── resources/
     
          ├── application.properties

⚙️ Database Schema (PostgreSQL)

      CREATE TABLE authors (

      id SERIAL PRIMARY KEY,

      name VARCHAR(100),
    
      email VARCHAR(100) UNIQUE,
    
      bio TEXT
      );


      CREATE TABLE blog_posts (

      id SERIAL PRIMARY KEY,
    
      title VARCHAR(255),
    
      content TEXT,
    
      created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    
      updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    
      author_id INT REFERENCES authors(id)
      
<img width="432" height="168" alt="authors_table" src="https://github.com/user-attachments/assets/c9cf3079-9f8e-4d08-9973-c00792b77606" />
<img width="1013" height="162" alt="blog_post table" src="https://github.com/user-attachments/assets/b26912f0-5262-479c-84f8-83ed62284cbc" />








