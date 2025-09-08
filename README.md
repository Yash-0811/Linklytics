# Linklytics
# URL Shortener with Authentication & Analytics

A secure and scalable URL Shortener built with Spring Boot.  
This application enables users to shorten long URLs, track analytics, and manage URLs with JWT-based authentication.

---

## Features

- **User Authentication & Authorization**
  - Register and log in with JWT-based security.
  - Role-based access control (`ROLE_USER`).

- **URL Shortening**
  - Generate short, shareable links.
  - Redirect seamlessly to the original URL.

- **Analytics & Tracking**
  - Track clicks for each short URL.
  - Retrieve analytics between date ranges.
  - Get total clicks grouped by date.

- **Secure APIs**
  - Spring Security with JWT protection.
  - Role-based access with `@PreAuthorize`.

---

## Tech Stack

- **Backend:** Java, Spring Boot, Spring Security, JWT  
- **Database:** MySQL / PostgreSQL / H2 (configurable)  
- **ORM:** Spring Data JPA (Hibernate)  
- **Build Tool:** Maven  
- **Other:** Lombok  

---

## API Endpoints

### Authentication
- `POST /api/auth/public/register` → Register a new user  
- `POST /api/auth/public/login` → Authenticate user and receive JWT  

### URL Shortening
- `POST /api/urls/shorten` → Create a short URL (requires `ROLE_USER`)  
- `GET /api/urls/myUrls` → Get all short URLs created by the user  

### Analytics
- `GET /api/urls/analytics/{shortUrl}?startDate&endDate` → Get analytics for a specific short URL  
- `GET /api/urls/totalClicks?startDate&endDate` → Get total clicks for all user URLs  

### Redirect
- `GET /{shortUrl}` → Redirect to the original URL  

---

## Setup and Installation

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/your-username/url-shortener.git
   cd url-shortener
