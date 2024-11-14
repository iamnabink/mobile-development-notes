React-native css things: https://chatgpt.com/share/6734c623-6f44-800f-91c7-4ce87f4868df

[ JavaScript Code ] --(Bridge)--> [ Native APIs ] --(UIKit/View)--> [ Screen ]

[ Dart Code ] --> [ Skia Rendering Engine ] --> [ Screen ]


React DOM is an web API for managing html element and java script bridge to update UI

React Update Flow

1. User Interaction / State Change
   ↓
2. Trigger re-render of component
   ↓
3. Create new Virtual DOM
   ↓
4. Diff new Virtual DOM with previous Virtual DOM
   ↓
5. Determine changes (what has changed)
   ↓
6. Update only the changed parts of the actual DOM
   ↓
7. Call component lifecycle methods (if applicable)


React Native Update Flow

├── Triggering an Update
│   ├── User Interaction (e.g., button press, text input change)
│   ├── State Change (using useState or this.setState)
│   └── Props Change (parent component updates props)
│
├── Re-rendering the Component
│   └── Mark the component for re-rendering
│
├── Creating a Virtual Representation
│   └── Generate a new virtual representation based on updated state/props
│
├── Diffing the Virtual Representation
│   └── Compare new virtual representation with the previous one
│       └── Identify changes (reconciliation)
│
├── Sending Updates to the Bridge
│   └── Send identified changes to the React Native bridge
│
├── Updating Native UI
│   └── Native thread processes updates received from the bridge
│       └── Update corresponding native components
│
├── Rendering Changes
│   └── Native rendering engine updates visual representation on screen
│
├── Component Lifecycle Methods
│   └── Execute lifecycle methods or hooks
│       └── Perform side effects (e.g., data fetching, animations)
│
└── Completion of Update
└── User sees the updated UI



React structure:

my-react-app/
├── node_modules/          # Contains all npm packages
├── public/                # Static files that will be served directly
│   ├── index.html         # The main HTML file
│   └── favicon.ico        # Favicon for the app
├── src/                   # Source files for the application
│   ├── components/        # Reusable components
│   │   ├── Header.js      # Header component
│   │   ├── Footer.js      # Footer component
│   │   └── ...            # Other components
│   ├── context/           # Context API files for state management
│   │   ├── AuthContext.js  # Example context for authentication
│   │   └── ...            # Other context files
│   ├── hooks/             # Custom hooks
│   │   ├── useAuth.js     # Example custom hook for authentication
│   │   └── ...            # Other hooks
│   ├── pages/             # Components representing different pages or views
│   │   ├── Home.js        # Home page component
│   │   ├── About.js       # About page component
│   │   └── ...            # Other pages
│   ├── App.js             # Main application component
│   ├── index.js           # Entry point of the application
│   ├── styles/            # CSS or style files
│   │   ├── App.css        # Global styles
│   │   └── ...            # Other styles
│   ├── utils/             # Utility functions or helpers
│   │   ├── api.js         # API call functions
│   │   └── ...            # Other utilities
│   └── ...                # Other files, such as images, etc.
├── .gitignore              # Specifies files to ignore in Git
├── package.json            # Project metadata and dependencies
├── package-lock.json       # Exact versions of installed packages
└── README.md               # Project documentation


React-Native: 
Context Based API  my-react-native-app/
├── android/               # Contains Android-specific code and configurations
├── ios/                   # Contains iOS-specific code and configurations
├── node_modules/         # Contains all npm packages
├── src/                   # Source files for the application
│   ├── components/        # Reusable components
│   │   ├── Button.js      # Custom button component
│   │   ├── Card.js        # Card component
│   │   └── ...            # Other components
│   ├── context/           # Context API files for state management
│   │   ├── AuthContext.js  # Example context for authentication
│   │   └── ...            # Other context files
│   ├── hooks/             # Custom hooks
│   │   ├── useAuth.js     # Example custom hook for authentication
│   │   └── ...            # Other hooks
│   ├── screens/           # Components representing different screens or views
│   │   ├── Home.js        # Home screen component
│   │   ├── Profile.js     # Profile screen component
│   │   └── ...            # Other screens
│   ├── navigation/        # Navigation setup (React Navigation)
│   │   ├── AppNavigator.js # Main app navigation
│   │   └── ...            # Other navigators or routes
│   ├── assets/            # Images, fonts, and other static assets
│   ├── App.js             # Main application component
│   ├── index.js           # Entry point of the application
│   ├── styles/            # Styles or CSS files (can also be JS objects)
│   │   ├── globalStyles.js # Global styles
│   │   └── ...            # Other styles
│   ├── utils/             # Utility functions or helpers
│   │   ├── api.js         # API call functions
│   │   └── ...            # Other utilities
│   └── ...                # Other files, as needed
├── .gitignore              # Specifies files to ignore in Git
├── package.json            # Project metadata and dependencies
├── package-lock.json       # Exact versions of installed packages
└── README.md               # Project documentation

Featured based architecture:  src/
├── features/
│   ├── Auth/
│   │   ├── components/    # Auth-related components
│   │   ├── hooks/         # Auth-related hooks
│   │   ├── screens/       # Auth screens (e.g., Login, Register)
│   │   ├── services/      # Auth-related services (API calls)
│   │   └── AuthContext.js  # Context for authentication state
│   ├── Products/
│   │   ├── components/
│   │   ├── screens/
│   │   ├── services/
│   │   └── ProductContext.js
│   └── ...

Redux Architecture

src/
├── actions/               # Redux action creators
│   ├── authActions.js
│   └── productActions.js
├── reducers/              # Redux reducers
│   ├── authReducer.js
│   └── productReducer.js
├── store/                 # Redux store configuration
│   └── store.js
├── components/            # UI components
├── screens/               # Screens for navigation
└── ...

Community Standards and Conventions
While many developers may start with the feature-based or MVC approaches, the choice of architecture often depends on the size and complexity of the application. The React Native community tends to lean towards:
* Feature-Based Architecture for modularity.
* Redux for state management in larger applications.
* Context API for smaller applications or simpler state management needs.


What Does react-scripts Provide?

react-scripts is a powerful tool that abstracts away the complexities of configuring a React application,

1. Webpack Configuration: Handles module bundling, code splitting, and optimization.
2. Babel Setup: Transpiles modern JavaScript and JSX to a version that is compatible with older browsers.
3. ESLint: Lints your code to help maintain quality and enforce coding standards.
4. Development Server: Provides a live reloading server during development.
5. Testing Setup: Comes pre-configured with Jest for running tests.
6. Build Scripts: Provides scripts for building the production-ready application.
