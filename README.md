# Dealerships Review Portal – Capstone Project

## Introduction

A national car dealership with branches across the United States wants a central website for customers to view dealership reviews, filter by state, and add their own reviews. This project implements a full-stack solution using Django, React, Node.js/Express, MongoDB, and Docker.

## Features

### Anonymous Users

- View Contact Us and About Us pages
- Browse dealerships and filter by state
- View dealership details and customer reviews
- Log in to access more features

### Authorized Users

- All anonymous user features
- Write reviews for dealerships
- Review form includes:
  - Dealer selection
  - Review text
  - Purchase checkbox
  - Purchase date (calendar)
  - Car make/model/year (dropdowns)
- Submitted reviews appear at the top, sorted by time

### Admin Users

- Log in to the admin site
- Add new car makes, models, and attributes

## Solution Architecture

**Frontend:** React (user registration, login, browsing, review submission)

**Backend:** Django (user management, car models/makes, proxy to microservices)

**Microservices:**

- Node.js/Express + MongoDB (dealers and reviews)
- Python Flask (sentiment analysis)

**Database:**

- SQLite (Django: car makes/models)
- MongoDB (dealers/reviews)

**Docker/Kubernetes:**

- All services containerized for deployment

## API Endpoints

### Django Application

- `/get_cars/` – List cars
- `/get_dealers/` – List dealers
- `/get_dealers/<state>` – Dealers by state
- `/dealer/<id>` – Dealer details
- `/reviews/dealer/<id>` – Dealer reviews
- `/add_review/` – Submit review

### Node.js/Express Service

- `/fetchDealers` – All dealers
- `/fetchDealer/:id` – Dealer by ID
- `/fetchReviews` – All reviews
- `/fetchReviews/dealer/:id` – Reviews by dealer
- `/insert_review` – Add review

### Sentiment Analyzer (Flask)

- `/analyze/:text` – Analyze review sentiment

## Setup & Running

1. **Clone the repository**
2. **Install dependencies** for each service:
   - Django: `pip install -r requirements.txt`
   - Node.js: `npm install` in `carsInventory` and `database`
   - React: `npm install` in `frontend`
3. **Run services locally**
   - Django: `python manage.py runserver`
   - Node.js: `node app.js` (ports 3030/3050)
   - React: `npm start`
4. **Docker/Kubernetes:**
   - Build and run containers as per provided Dockerfiles and deployment.yaml

## Project Breakdown

- Static pages for user stories
- User management (Django + React)
- Backend microservices (Node.js/Express, MongoDB, Flask)
- Django models/views for car data
- Proxy integration for reviews/dealers
- Dynamic pages with Django templates
- CI/CD setup
- Cloud/Kubernetes deployment

## Screenshots

Screenshots of the application and its features are available in the [Images folder](Images/).
These images illustrate key pages, user flows, and deployment steps for the project.
