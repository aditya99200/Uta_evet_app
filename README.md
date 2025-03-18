# Flask Event Management App

## Overview
This is an industrial-grade Flask-based backend for an event management app similar to Whova. It provides features such as user authentication, event and agenda management, payments, and real-time networking via WebSockets.

## Features
- **User Authentication**: JWT-based authentication system.
- **Event Management**: Create, retrieve, and manage events.
- **Agenda Management**: Manage event schedules and speaker details.
- **Payments**: Integrated with Stripe for secure transactions.
- **Real-time Networking**: WebSocket-based real-time chat.
- **Database Support**: Uses PostgreSQL for scalability.
- **Logging & Monitoring**: Integrated logging for debugging and monitoring.
- **CORS Handling**: Allows cross-origin API access.

## Technologies Used
- **Flask**: Backend framework
- **Flask-JWT-Extended**: Authentication
- **Flask-SQLAlchemy**: ORM for database management
- **Flask-SocketIO**: Real-time messaging
- **PostgreSQL**: Database
- **Stripe API**: Payment processing
- **Logging**: Application monitoring

## Setup Instructions

### Prerequisites
- Python 3.x
- PostgreSQL database

 Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/flask-event-app.git
   cd flask-event-app
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Configure environment variables (e.g., `.env` file):
   ```
   DATABASE_URL=postgresql://user:password@localhost/db_name
   JWT_SECRET_KEY=your_jwt_secret
   STRIPE_SECRET_KEY=your_stripe_secret_key
   ```

 Running the Application
1. Initialize the database:
   ```bash
   flask db upgrade
   ```
2. Start the Flask server:
   ```bash
   python app.py
   ```
3. Run WebSocket server:
   ```bash
   python -m flask run --host=0.0.0.0 --port=5000
   ```
 API Endpoints
- `POST /register` - Register a new user
- `POST /login` - Authenticate and retrieve JWT token
- `GET /events` - Fetch all events
- `POST /events` - Create an event (Authenticated)
- `GET /agenda/<event_id>` - Get agenda for a specific event
- `POST /pay` - Make a payment for an event (Authenticated)
- WebSocket messaging via `/socket.io`

 Deployment
- **Docker**: Create a `Dockerfile` and deploy using Kubernetes or Docker Compose.
- **AWS Deployment**: Use Elastic Beanstalk or Lambda with API Gateway.

Contribution
Feel free to contribute by submitting a pull request. Follow the standard PR guidelines.

## License
MIT License

