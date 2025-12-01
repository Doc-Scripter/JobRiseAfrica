# JobRise Africa

JobRise Africa is a web application dedicated to helping job seekers across the African continent find verified job opportunities directly from official company career pages. The platform crawls and aggregates listings from trusted sources, ensuring that users access genuine, up-to-date opportunities.

This README provides an overview of the system architecture, setup requirements, development workflow, and contribution guidelines.

## Overview

JobRise Africa offers curated job listings sourced from company websites. Users can browse opportunities, save or bookmark jobs locally without an account, and access a clean, fast, and reliable interface built for the African job market.

## Features

* Aggregates jobs by crawling official company career pages.
* Clean, intuitive user interface built with Vue.js.
* Server-side API built with Flask for job aggregation and data processing.
* Local caching for saving or bookmarking jobs without requiring account creation.
* Deployment with separate frontend and backend infrastructure.
* “Non-Commercial Use Only” license requirement for public usage.

## Architecture

JobRise Africa is built using a modular, modern architecture:

### Frontend

* Built with Vue.js.
* Handles job browsing, search, filters, bookmarks, and UI interactions.
* Stateless with respect to user authentication until full account functionality is implemented.
* Deployed on Vercel.

### Backend

* Developed using Python Flask.
* Handles the crawling engine, API endpoints, job data processing, and caching logic.
* Deployed on Render.

### Database

* Supabase serves as the primary database.
* Stores job entries, crawl metadata, logs, and future user accounts.

### Crawling Layer

* Scheduled crawlers fetch jobs from known company career pages.
* Each crawler normalizes job fields such as title, company, location, description, and apply URL.
* Deduplication logic prevents repeated listings.
* Error-handling and logging track failed or changed job sources.

### Bookmarking

* Users can save jobs without creating an account.
* Bookmark data is stored in browser cache (localStorage) until account features are introduced.

### Deployment Flow

* Frontend deployed on Vercel.
* Backend deployed on Render.
* Supabase provides database hosting.
* Crawler scheduling can run via Render cron jobs or external schedulers.

## Local Setup

### Requirements

* Python 3.10+
* Node.js 18+
* Vue.js CLI
* Virtual environment for backend

### Backend Setup

1. Clone the repository.
2. Navigate to the backend directory.
3. Create and activate a virtual environment.
4. Install dependencies with `pip install -r requirements.txt`.
5. Create an `.env` file with necessary environment variables.
6. Run the Flask development server.

### Frontend Setup

1. Navigate to the frontend directory.
2. Install dependencies with `npm install`.
3. Create a `.env` file for API configuration.
4. Start the frontend using `npm run dev`.

## Deployment

* Frontend is configured to deploy on Vercel.
* Backend is configured to deploy on Render.
* Environment variables should be set in each platform for production.
* Supabase hosts the production database.

## License

This project includes a custom license: **Non-Commercial Use Only**.
No person or organization may sell, redistribute commercially, or use the platform or its aggregated data for commercial gain without explicit permission.

## Contributions

Contributions are welcome and encouraged.
To contribute:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Write clean, documented code.
4. Ensure that changes do not break existing functionality.
5. Submit a pull request describing your changes in detail.

All contributions will be reviewed before merging.

## Roadmap

* Add user accounts and authentication.
* Enhance crawling accuracy with machine-assisted validation.
* Add email job alerts.
* Add analytics dashboards for job trends.
* Support employer account onboarding.

## Contact

For inquiries, permissions, or collaboration opportunities, contact the project maintainer.
