mafia-backend/
├── src/
│   ├── app.js                      # Main Express app configuration
│   ├── server.js                   # Server startup
│   │
│   ├── config/
│   │   ├── database.js             # MongoDB connection
│   │   └── config.js               # App settings (ports, URLs, etc.)
│   │
│   ├── models/                     # Database schemas (Developer 1 focus
│   │   ├── User.js                 # Users (patients, admins)
│   │   ├── Facility.js             # Hospitals, pharmacies, labs
│   │   ├── Medication.js           # Available medications
│   │   ├── Test.js                 # Medical tests available
│   │   ├── Emergency.js            # Emergency requests/alerts
│   │   └── Inventory.js            # Real-time stock tracking
│   │
│   ├── controllers/                # Business logic (Split between developers)
│   │   ├── authController.js       # Login, registration, roles
│   │   ├── userController.js       # User management
│   │   ├── facilityController.js   # Facility management
│   │   ├── medicationController.js # Medication search & availability
│   │   ├── testController.js       # Test booking & availability
│   │   ├── emergencyController.js  # Emergency request handling
│   │   └── adminController.js      # Admin dashboard operations
│   │
│   ├── routes/                     # API endpoints (Developer 2 focus)
│   │   ├── auth.js                 # POST /login, /register, /logout
│   │   ├── users.js                # GET/PUT /users/:id
│   │   ├── facilities.js           # GET /facilities, /facilities/nearby
│   │   ├── medications.js          # GET /medications/search, /availability
│   │   ├── tests.js                # GET /tests/search, POST /tests/book
│   │   ├── emergency.js            # POST /emergency/request
│   │   └── admin.js                # Admin dashboard routes
│   │
│   ├── middleware/                 # Custom middleware
│   │   ├── auth.js                 # JWT token verification
│   │   ├── validation.js           # Input validation
│   │   ├── errorHandler.js         # Global error handling
│   │   └── adminAuth.js            # Admin-only route protection
│   │
│   ├── utils/                      # Helper functions
│   │   ├── helpers.js              # General utilities
│   │   ├── validation.js           # Input validation rules
│   │   ├── constants.js            # App constants
│   │   └── geolocation.js          # Location-based search
│   │
│   └── services/                   # External integrations
│       ├── emailService.js         # Email notifications
│       ├── smsService.js           # SMS alerts for emergencies
│       └── mapService.js           # Google Maps API integration
│
├── tests/                          # Simple testing setup
│   ├── auth.test.js                # Authentication tests
│   ├── medication.test.js          # Medication search tests
│   └── emergency.test.js           # Emergency request tests
│
├── docs/                           # Documentation
│   ├── API.md                      # API documentation
│   ├── SETUP.md                    # Development setup guide
│   └── DEPLOYMENT.md               # Deployment instructions
│
├── .env.example                    # Environment variables template
├── .env                            # Actual environment variables (gitignored)
├── .gitignore                      # Git ignore file
├── package.json                    # Dependencies and scripts
├── README.md                       # Project overview
└── docker-compose.yml              # Optional: for consistent dev environment

// =============================================================================
// DEVELOPER TASK DIVISION SUGGESTION
// =============================================================================

/* 
DEVELOPER 1 - Backend Core & Models
- Database schema design (models/)
- Authentication system (authController.js, auth.js middleware)
- User management (userController.js, users.js routes)
- Database setup and connections

DEVELOPER 2 - Features & Admin System  
- Medication/Test search (medicationController.js, testController.js)
- Emergency requests (emergencyController.js, emergency.js routes)
- Admin dashboard (adminController.js, admin.js routes)
- External services integration (services/)
