# Data Quality Rule Execution Framework

This is a Flask-based application that allows users to run and track the execution of data quality rules. The framework supports real-time updates on the execution status and results, and provides endpoints for users to initiate rule execution and cancel ongoing executions.

## Features
- **Run Data Quality Rules**: Users can trigger data quality rule executions.
- **Real-Time Execution Progress**: Monitor rule execution progress in real-time via WebSockets.
- **Cancel Executions**: Cancel ongoing rule executions if necessary.
- **Historical Execution Data**: View the history of previously executed rules.
- **User Authentication**: Secure API endpoints using JWT-based authentication.
- **Admin Interface**: Provides a user-friendly admin UI for managing executions and viewing status updates.

## Tech Stack
- **Backend**: Python 3.9 with Flask
- **Database**: SQLite for storing execution data
- **Authentication**: JWT-based authentication (Flask-JWT-Extended)
- **WebSockets**: Flask-SocketIO for real-time updates
- **Cache**: Redis for caching historical execution data
- **Frontend**: HTML, Bootstrap, and JavaScript for the user interface

## Requirements
To run the application locally, you need Python 3.9 or higher and the following libraries:

```txt
Flask==2.2.3
Flask-SQLAlchemy==2.5.1
Flask-JWT-Extended==4.4.4
Flask-SocketIO==5.3.0
Flask-Caching==1.10.1
redis==4.4.0
eventlet==0.33.0
```

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/data-quality-framework.git
   cd data-quality-framework
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**:
   ```bash
   flask run
   ```

   The app will be available at `http://localhost:5000`.

## Usage

### **Running a Rule**
1. Open the application in your browser.
2. In the "Run Data Quality Rule" section, enter the rule name.
3. Click the **Run Rule** button.
4. You will see real-time updates on the execution status.

### **Canceling an Execution**
1. If you need to cancel an ongoing execution, click the **Cancel** button next to the rule execution in the table.
2. The system will immediately stop the execution, and the status will update to "Cancelled."

### **Viewing Execution History**
1. The historical execution data is available in the table below the rule execution section.
2. This data is cached and displayed from Redis for faster access.

### **Admin Interface**
- The application includes an admin UI for monitoring rule execution progress.
- You can track multiple rules being executed simultaneously and view their detailed status.

## WebSocket Support
The application supports real-time updates using WebSockets. When a rule is executed, users connected via WebSocket will receive updates on the status and results of the execution. This is done via `Flask-SocketIO`.

## Docker Setup (Optional)

You can containerize the application and run it with Docker using the following steps:

1. **Build the Docker image**:
   ```bash
   docker build -t data-quality-framework .
   ```

2. **Run the application using Docker Compose**:
   ```bash
   docker-compose up
   ```

   This will set up both the Flask app and Redis service, and you can access the app at `http://localhost:5000`.

## Contributing
Feel free to contribute to this project by submitting issues and pull requests. To get started:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature/your-feature`).
6. Create a pull request.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Let me know if you'd like any adjustments!
