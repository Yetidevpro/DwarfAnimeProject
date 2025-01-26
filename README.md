# DwarfAnimeProject

**DwarfAnimeProject** is a full-stack application designed to manage anime data with a **REST API backend** built using **ASP.NET Core (C#)** and a **JavaScript frontend** for managing user interactions. The project allows users to interact with a dynamic anime list, create and manage accounts, rate animes, and view personal ratings. Both the backend and frontend are deployed on **Azure Services**, offering scalability, reliability, and accessibility.

The project consists of two main parts:

- **DwarfAnimeBackend**: This is the backend API that serves as the central logic of the application. It manages all the data interactions, such as retrieving anime information from the database, handling user authentication, and performing CRUD operations.
  
- **DwarfAnimeFrontend**: The frontend is responsible for presenting the user interface, interacting with the backend API, and displaying anime data. It allows users to manage their profile, add new animes, and rate animes from the database.

## Project Structure

The project is divided into two main parts, each serving a specific purpose:

### Backend (DwarfAnimeBackend)

The backend of this project is implemented using **ASP.NET Core (C#)**. It exposes a RESTful API that provides endpoints for various operations like managing anime data, user authentication, and user ratings. The backend also integrates with a **SQL database** to persist the data.

#### Key Features

1. **REST API Implementation**:
   - The API consists of several endpoints exposed via **Controllers** in **ASP.NET Core**. These endpoints allow users to interact with the anime database, rate animes, and manage user accounts.
   - Each controller is responsible for a specific set of actions, such as managing the list of animes, authenticating users, or handling ratings.

2. **Database Management**:
   - The backend uses **Entity Framework Core (ORM)** to interact with a **SQL database**, which simplifies the data management process without the need for writing raw SQL queries.
   - **Models** represent the entities in the database, such as users and animes. **Migrations** are used to update the database schema automatically when changes are made to the models.

3. **User Authentication**:
   - The backend supports user authentication, allowing users to create accounts, log in, and interact with the system based on their credentials.
   - Passwords are hashed securely (currently without advanced encryption, but future updates will include **PBKDF2** for secure password hashing).

4. **Anime Management**:
   - Users can add new animes to the database, and the anime list can be viewed, sorted, and interacted with. 
   - The API also supports updating anime information and deleting anime entries.

#### Future Updates for Backend

1. **Secure Password Hashing**:
   - Implement **PBKDF2** or other secure hashing algorithms for better protection of user passwords.

2. **Extended API Functionalities**:
   - Add more endpoints for user interactions, such as editing user profiles, modifying ratings, or deleting user accounts.
   - Enable users to modify or delete anime entries, adding more flexibility to the anime database management system.

3. **API for Blog and Comments**:
   - Integrate a system for users to post blogs or leave comments on anime entries. This would allow users to engage in discussions and reviews.

### Frontend (DwarfAnimeFrontend)

The frontend is built using **JavaScript**, **HTML**, and **CSS**. It provides the user interface for interacting with the backend API, allowing users to manage their anime list, rate animes, and manage their profile.

#### Key Features

1. **Anime List Display**:
   - The home page shows a dynamic list of all the animes present in the database. Users can interact with this list to add new animes or view detailed information about each one.

2. **User Management**:
   - Users can create new accounts or log into existing accounts via the login page.
   - After logging in, users are directed to their personal page, where they can view and manage their anime list, and rate animes.

3. **User Ratings**:
   - Users can rate animes on a scale (e.g., 1-10) once logged in. After rating an anime, the rating cannot be modified to ensure consistency.
   - The user’s anime ratings are saved and displayed in their personal list.

4. **Responsive Design**:
   - The frontend is designed to be mobile-responsive, ensuring that the interface is accessible across devices of different screen sizes.

#### Future Updates for Frontend

1. **Enhanced Visual Design**:
   - The current UI will be revamped with a more modern and visually appealing design. Focus will be placed on creating an engaging and interactive experience for the user.
   
2. **Advanced API Integrations**:
   - Add functionality for users to edit their profiles, modify their ratings, delete accounts, and interact with anime data in more sophisticated ways.
   
3. **Blog and Comment Sections**:
   - Add a **blog system** where users can write posts or reviews about animes, along with a comment section for each anime for users to share their thoughts.
   
4. **User Interaction**:
   - Improve the interaction features to include rating validation, notifications, and real-time updates for rating changes or new anime additions.

## Deployment

Both the backend and frontend of **DwarfAnimeProject** are deployed in **Azure Services**:

- The **backend** (DwarfAnimeBackend) is deployed as a RESTful API on **Azure App Services**, while the **SQL database** is hosted on **Azure SQL Database** for performance and scalability.
- The **frontend** (DwarfAnimeFrontend) is deployed on **Azure Web Apps**, ensuring a cloud-based, highly available web application.

## Installation

### Prerequisites

- **.NET Core 6** or higher for the backend.
- A modern web browser (Chrome, Firefox, Safari, etc.) for the frontend.
- An **Azure account** if you wish to deploy the services yourself.

### Running the Backend Locally

1. **Clone the repository**:
   ```bash
     git clone https://github.com/yourusername/DwarfAnimeBackend.git

2. **Navigate to the DwarfAnimeBackend directory and restore dependencies**:
   ```bash
      cd DwarfAnimeBackend
      dotnet restore

3. **Update the database connection in the appsettings.json file to use your local database or configure it for Azure.**

4. **Apply the migrations to create/update the database schema:**
   ```bash
    dotnet ef database update

5. **Run the API locally:**
    ```bash
      dotnet run

## Running the Frontend Locally

1. **Clone the frontend repository**:
    ```bash
       git clone https://github.com/yourusername/DwarfAnimeFrontend.git
    
2. **Open the index.html file in your browser.**

3. **Ensure that the DwarfAnimeBackend API is running locally or hosted on Azure for the frontend to communicate properly.**
