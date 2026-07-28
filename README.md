# LocalConcerts

LocalConcerts is a full-stack Flask web application for discovering, creating, and booking local concert events.

The app gives users a polished event browsing experience with search, genre filters, featured event cards, ticket availability, authentication, booking history, event management, and comments. It was built as a university group project and demonstrates practical full-stack development with Flask, SQLAlchemy, WTForms, Bootstrap, and SQLite.

## Project Highlights

- Responsive concert discovery interface with Bootstrap 5
- User registration, login, logout, and session-based access control
- Search by event title, venue, genre, or description
- Genre filtering and quick filters for today, this week, and events under $50
- Featured event carousel and event card grid
- Event detail pages with ticket availability and comments
- General Admission and VIP ticket booking
- Booking history dashboard with order IDs and ticket details
- Authenticated event creation and owner-only event editing
- Event owner actions for cancelling, reopening, or marking events as sold out
- Form validation using WTForms
- SQLite database with SQLAlchemy models and relationships
- Custom 404 and 500 error pages
- Seed data for realistic demo events, users, bookings, and comments

## Why This Project Matters

LocalConcerts is more than a static event listing page. It includes multiple connected workflows that are common in real web applications:

- users can create accounts and log in
- event owners can create and manage events
- customers can browse, filter, and book tickets
- the system tracks ticket availability across General Admission and VIP ticket types
- comments and bookings are persisted in a database
- UI state changes based on authentication, ownership, event status, and ticket availability

For a junior full-stack developer role, this project demonstrates the ability to build a database-backed web app with routing, templates, forms, authentication, validation, relational models, and a responsive user interface.

## Tech Stack

- Python
- Flask
- Flask Blueprints
- Flask-Login
- Flask-WTF / WTForms
- Flask-SQLAlchemy
- Flask-Bcrypt
- SQLite
- HTML
- CSS
- Bootstrap 5
- Bootstrap Icons
- Jinja templates

## Core Features

### Event Discovery

Users can browse upcoming and past events from the homepage. Events are displayed using responsive cards with imagery, venue details, dates, pricing, ticket availability, and status badges.

Discovery features include:

- search bar
- genre dropdown
- quick filters
- featured events carousel
- upcoming and past event sections

### Authentication

The app supports account registration, login, and logout. Authentication is handled with Flask-Login, and passwords are stored as hashes.

Registered users can:

- book tickets
- view their booking history
- create events
- edit their own events
- comment on event pages

### Event Management

Authenticated users can create new concert events with:

- event name
- venue
- description
- date and time
- General Admission price
- optional VIP price
- category
- ticket capacities
- image URL

Event owners can edit their own events and manage event status by cancelling, reopening, or marking an event as sold out.

### Ticket Booking

Users can book either General Admission or VIP tickets when available. The booking flow checks ticket availability before creating an order.

The app tracks:

- General Admission capacity
- VIP capacity
- tickets sold by ticket type
- remaining tickets
- sold-out state
- booking history per user

### Comments

Logged-in users can post comments on event detail pages. Comments are stored in the database and displayed with the author and timestamp.

## Application Structure

```text
LocalConcerts/
  main.py
  seed_data.py
  requirements.txt
  instance/
    sitedata.sqlite
  website/
    __init__.py
    auth.py
    forms.py
    models.py
    views.py
    static/
      img/
      style/
    templates/
      errors/
      bookings.html
      create.html
      event.html
      index.html
      user.html
```

## Data Model

The application uses SQLAlchemy models for:

- `User` - registered users, profile details, events, orders, and comments
- `Event` - concert details, pricing, status, capacities, owner, comments, and orders
- `Order` - ticket bookings linked to users and events
- `Comment` - user comments linked to events

## Getting Started

### Prerequisites

- Python 3
- pip
- virtual environment recommended

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run the Application

```bash
python main.py
```

Then open the local Flask URL in your browser, usually:

```text
http://127.0.0.1:5000
```

### Seed Demo Data

The repository includes `seed_data.py`, which inserts demo users, events, bookings, and comments if the database is empty.

```bash
python seed_data.py
```

## Deployment

This project was prepared as a Flask web app suitable for deployment on PythonAnywhere. The live deployment URL is not currently stored in the repository; it can be added here when the active PythonAnywhere URL is confirmed.

## Validation

The project has been checked with Python bytecode compilation:

```bash
python3 -m compileall website main.py seed_data.py
```

## Future Improvements

- Add automated tests for booking, filtering, authentication, and event management flows
- Move the secret key and database settings into environment variables
- Add a production-ready deployment configuration section
- Add screenshots or a short demo GIF to improve portfolio presentation
- Add payment-provider integration for realistic ticket checkout
- Add admin/moderator tools for managing inappropriate comments or events

## Team

This project was developed as a university group assignment. My work focused on contributing to the Flask application structure, user-facing workflows, event functionality, and project integration.
