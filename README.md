# gcp-diagram-socialmediaapplication

**********
Task:
Scenario 3: Social Media Application

Architecture:
1. Presentation Tier (Frontend):
  - Components:Web browser, Mobile app.
  - Technologies:Vue.js, HTML, CSS, JavaScript, React Native.
2. Application Tier (Backend):
  - Components:Web server, API server.
  - Technologies:** Go with Gin, Node.js with Express.js, Java with Spring Boot.
3. Data Tier (Database):
  - Components:Database server, Cache server.
  - Technologies:** MongoDB (for user posts), Redis (for caching frequently accessed data).
Scenario:
A social media application where users can create profiles, post updates, and interact with each other's content.
- User Interaction:Users interact with the website or mobile app to create profiles, post updates, and comment/like posts.
- Business Logic:The backend server handles user authentication, post creation, and social interactions.
- Data Storage:User profiles, posts, comments, and likes are stored in the database, with frequently accessed data cached for performance.
Flow:
1. The user logs in to the social media application via the website or mobile app.
2. The frontend requests the user's feed from the backend.
3. The backend retrieves posts from the database and caches frequently accessed posts in Redis.
4. The backend sends the feed data to the frontend to display to the user.
5. The user creates a new post, which the backend processes and stores in the database.
6. The user's friends interact with the post (like, comment), and the backend updates the database accordingly.
************

Diagram:
![GCP - Scenario 3](https://github.com/user-attachments/assets/d2de7e4a-8205-42a7-9d3f-45abb713a7dc)

Explanation: 3 regions used to ensure 99.999% availability and to be fault tolerant
- Cloud load balancer used to spread load across availability zones
- Web tier and application tier for frontend and backend
- Compute engine used for web and app servers
- Cloud memorystore used for database - Memorystore is a fully-managed database service that provides a managed version of two popular open source caching solutions: Redis and Memcached
