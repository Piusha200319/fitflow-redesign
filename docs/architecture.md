FitFlow — High-Level Architecture (Activity 4)

See architecture-diagram.png in this folder for the full visual diagram.

Key Components
•	Client Layer: Consists of the React Native Mobile App for iOS and Android, alongside the React Native Web App which utilizes a shared codebase. Both client interfaces implement Local SQLite Caching for offline data management. 
•	Gateway & Authentication Layer: Features an API Gateway built with Express.js that manages incoming REST and WebSocket connections. Client authentication is securely handled in this layer using Firebase Auth via JWT and OAuth protocols. 
•	Application Services Layer: Houses the Core Backend constructed with Node.js and Express to orchestrate primary business logic. This layer also integrates Firebase-powered Analytics & Monitoring services. 
•	AI & Advanced Services Layer: Contains the AI Microservice, leveraging TensorFlow Lite and Cloud ML specifically for workout personalization. It also includes a dedicated Computer Vision Service responsible for nutrition recognition and food logging. 
•	Data & Storage Layer: Comprises Firebase Firestore for managing structured user and workout data, and a Realtime Database for the social feed and chat functionalities. A Redis Cache is utilized for high-speed access to hot data and sessions, while Cloud Storage is dedicated to holding media and photos.

Data Flows for Critical Features
•	Personalized Workout Plans (Yellow Flow): The client requests a workout plan through the API Gateway, which routes the request to the Core Backend. The Core Backend triggers the AI Microservice for workout personalization, which retrieves the necessary data for context from Firebase Firestore before returning the customized plan. 
•	Social Sharing (Blue Flow): Social interactions from the Client Layer pass through the API Gateway to the Core Backend, which writes the updates to the Realtime Database. Live updates are subsequently pushed back to clients via WebSocket connections, while engagement metrics are captured by Analytics & Monitoring. 
•	Nutrition Tracking (Green Flow): A food logging request is sent from the client to the Core Backend via the API Gateway. The Core Backend communicates with the Computer Vision Service for nutrition recognition, which interacts directly with Cloud Storage to process and log the food media. 

Security, Scalability & Integration Considerations
•	Security: Client authorization is strictly enforced at the Gateway & Authentication Layer, with Firebase Auth validating JWT and OAuth tokens before requests reach the Application Services Layer. 
•	Scalability: The architecture separates the Application Services Layer from the Data & Storage Layer, allowing the Node.js/Express Core Backend to scale horizontally. Read-heavy operations are optimized using the Redis Cache for hot data and sessions, protecting the primary databases from overload. 
•	Integration: Heavy computational tasks are isolated within the AI & Advanced Services Layer. By keeping the AI Microservice and Computer Vision Service separated from the Core Backend, they can be independently updated, retrained, or scaled without disrupting primary application workflows. 
