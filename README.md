# Spring Boot Security with Google OAuth2

This project demonstrates how to implement Google OAuth2 authentication in a Spring Boot application.

## Features

- Google OAuth2 login
- User information display
- Secure session management
- Responsive UI

## Prerequisites

- Java 21
- Gradle
- Google Cloud Platform account

## Setup

### 1. Google Cloud Platform Setup

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Navigate to "APIs & Services" > "Credentials"
4. Click "Create Credentials" and select "OAuth client ID"
5. Select "Web application" as the application type
6. Add a name for your OAuth client
7. Add authorized redirect URIs:
    - `http://localhost:8080/login/oauth2/code/google` (for local development)
8. Click "Create"
9. Note your Client ID and Client Secret

### 2. Application Configuration

1. Clone this repository
2. Update the `application.yaml` file with your Google OAuth2 credentials:
   ```yaml
   spring:
     security:
       oauth2:
         client:
           registration:
             google:
               client-id: your-client-id
               client-secret: your-client-secret
   ```

   Alternatively, you can set these as environment variables:
   ```
   GOOGLE_CLIENT_ID=your-client-id
   GOOGLE_CLIENT_SECRET=your-client-secret
   ```

## Running the Application

```bash
./gradlew bootRun
```

Then navigate to `http://localhost:8080` in your web browser.

## Project Structure

- `SecurityConfig.java`: Spring Security configuration
- `HomeController.java`: Controller for handling requests
- `application.yaml`: Application configuration
- `templates/`: Thymeleaf templates for UI

## Security Features

- OAuth2 authentication with Google
- CSRF protection
- Secure session cookies
- Authorization controls

## License

This project is licensed under the MIT License - see the LICENSE file for details.