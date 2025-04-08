# DinoJump Game

A simple jumping dinosaur game.

## Features

- Simple dinosaur jumping game
- Local high score tracking
- Leaderboard display
- Score management

## Setup

### Prerequisites

- A modern web browser

### Local Development

1. Clone the repository
2. No installation needed - this is a standalone HTML game
3. Open the index.html file in your browser to play the game

### Azure Deployment

This project is configured for automatic deployment to Azure Web App using GitHub Actions.

To set up the deployment:

1. Create an Azure Web App
2. Set up the following GitHub Secrets in your repository:
   - `AZURE_WEBAPP_NAME`: The name of your Azure Web App
   - `AZURE_WEBAPP_PUBLISH_PROFILE`: The publish profile from your Azure Web App

3. Push to the main branch to trigger deployment

## Database Structure

The application uses a single table called `high_scores` in the PostgreSQL database with the following structure:

```sql
CREATE TABLE high_scores (
  id SERIAL PRIMARY KEY,
  score INTEGER NOT NULL,
  date TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```

## API Endpoints

- `POST /api/scores` - Save a new score
- `GET /api/scores?limit=10` - Get top scores (default limit is 5)
- `DELETE /api/scores` - Clear all scores