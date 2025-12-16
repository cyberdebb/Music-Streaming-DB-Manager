# Music Streaming DB Manager

## Overview
The project implements a **database management system for a music and podcast streaming platform**, focusing on data modeling, storage, retrieval, and management.

The system is designed to support users, subscription plans, playlists, media consumption history, and recommendation-related queries using a well-structured relational database.

---

## System Objective
The main objective of this system is to provide a platform where users can **access and enjoy a large collection of music and podcasts**, according to their subscription plan. Users can create playlists, view their playback history, and receive **recommendations based on the genre and theme of the media they consume most frequently**.

The system aims to be **reliable, user-friendly, and efficient**, ensuring proper **data management and retrieval** through a carefully designed database schema.

---

## System Features
- User registration and data storage
- Subscription plan management
- Playlist creation and management
- Music and podcast catalog
- Playback history tracking
- Artist, album, and creator information management
- Support for recommendation-related queries

---

## Conceptual Model

<img width="1006" height="789" alt="image" src="https://github.com/user-attachments/assets/5642883d-538d-4280-957c-4cdfd6f00b10" />

---

## Logical Model

<img width="974" height="734" alt="image" src="https://github.com/user-attachments/assets/879c600f-d3f9-4bc4-857d-0921863ecd8f" />

---

## Database Design Description

### Users
Each user is identified by:
- Email
- Name
- CPF (Brazilian individual taxpayer registry)

---

### Subscription Plans
- Every user must have **one subscription plan**
- Available plans:
  - **Standard (free)**
  - **Plus**
  - **Deluxe**
- Each plan includes:
  - Description
  - Price
  - Benefits
  - Start date
  - Expiration date (null for free plans)
- A plan can be associated with multiple users

---

### Playlists
- Users can create playlists to group media (music or podcasts)
- Each playlist has:
  - Name
  - Description
- A user may have multiple playlists
- Each playlist belongs to a single user

---

### Media Management
- Media types:
  - **Music** (associated with a genre)
  - **Podcast** (associated with a theme)
- Media attributes include:
  - Name
  - Duration
  - Release date
  - Number of reproductions (streams)
- Playback history stores:
  - User
  - Media
  - Playback date
- Many-to-many relationship:
  - Users ↔ Media
- Media can be included in playlists

---

### Creators and Authors
- **Music**:
  - Belongs to an album
  - Albums belong to an artist
  - Album attributes:
    - Name
    - Release year
    - Type (single or album)
  - Artists may be solo singers or bands
  - Artist attributes:
    - Name
    - Nationality
- **Podcasts**:
  - Authored by a podcaster
  - Podcaster attributes:
    - Name
    - Description

---

## Technology Stack
- **Python**
- **PostgreSQL**
- **psycopg2**
- **pydub**
- **matplotlib**
- **simpleaudio**

---

## How to Run the Project

### Prerequisites
- Python installed on your system
- PostgreSQL database configured

### Virtual Environment Setup
Create a virtual environment:
```sh
python -m venv env
```

### Activate the virtual environment:

Windows
```sh
env\Scripts\activate
```

Linux
```sh
source env/bin/activate
```

### Dependencies

Install the required libraries using pip:
```sh
pip install psycopg2
pip install pydub
pip install -U matplotlib
pip install simpleaudio
```

### Run the main file

```sh
python main.py
```

---

## Notes
- This project was developed for academic purposes
- The database model was designed specifically for PostgreSQL
- The system supports complex queries to enhance user experience and recommendation logic
