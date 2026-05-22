# JobSprint - Job Placement Tracker

A Flutter application designed to track and manage job placements and opportunities. JobSprint allows users to view, add, edit, and delete job placement records with comprehensive filtering and persistent storage capabilities.

**Version:** 1.0.0

## 🎯 Project Overview

JobSprint is a mobile application that helps users organize and track job placement opportunities. It provides an intuitive interface to manage job listings with detailed information including company details, work type, package, qualifications, and location-based filtering.

### Key Features

- **View Job Placements**: Browse all available job placements with detailed information
- **Add New Jobs**: Create new job placement records with comprehensive details
- **Edit Placements**: Update existing job placement information
- **Delete Records**: Remove outdated or irrelevant placements
- **City-based Filtering**: Filter placements by location to find jobs in specific cities
- **Persistent Storage**: All data is automatically saved using SharedPreferences
- **Beautiful UI**: Modern gradient design with an intuitive user interface
- **Responsive Design**: Adapts to different screen sizes

## 📁 Project Structure

```
lib/
├── main.dart                              # Application entry point
└── src/
    ├── assets/
    │   ├── logo.png                      # App logo
    │   └── background.png                # Background image
    └── features/
        └── authentication/
            ├── presentation/
            │   └── screens/
            │       ├── splashscreen.dart      # Splash/Loading screen
            │       ├── homepage.dart          # Main job listings screen
            │       ├── add_screen.dart        # Add new job placement form
            │       └── edit_screen.dart       # Edit job placement form
            └── widgets/
                └── fragment_holder.dart       # Navigation controller & data models
```

## 📱 File Details

### **main.dart**

- **Purpose**: Application entry point
- **What it does**: Initializes the Flutter app with MaterialApp configuration
- **Features**:
  - Sets app theme with custom color scheme
  - Disables debug banner
  - Sets initial route to SplashScreen
  - Defines global Material design theme

### **splashscreen.dart**

- **Purpose**: Loading/Welcome screen shown on app startup
- **What it does**:
  - Displays a 3-second splash screen with gradient background
  - Shows app logo and loading indicator
  - Preloads job placement data from storage
  - Navigates to main home screen after loading
- **UI Elements**:
  - Gradient background (Navy to Teal)
  - App logo (200px)
  - Loading spinner
  - Version display (v1.0)
  - Copyright notice

### **homepage.dart**

- **Purpose**: Main screen displaying all job placements
- **What it does**:
  - Lists all job placements in card format
  - Implements city-based filtering with dropdown
  - Provides edit and delete functionality for each placement
  - Has action button to add new placements
- **Key Components**:
  - **Color Palette**: Defines custom colors (kPrimary, kSecondary, kAccent, kHighlight)
  - **AppBar**: Displays "Job Placements" title with logo and add button
  - **City Filter**: Dropdown to filter jobs by location
  - **Job Cards**: Display job details with gradient background
    - Shows: Company name, location, department, package, work type, company size, position type, qualification
    - Edit and Delete buttons for each card
  - **Background**: Layered background image with semi-transparent overlay

### **add_screen.dart**

- **Purpose**: Form to add new job placement records
- **What it does**:
  - Provides 8 input fields for comprehensive job information
  - Validates and creates new HomeItem objects
  - Adds location to cities list for filtering
  - Returns to home screen after submission
  - Saves updated data to persistent storage
- **Input Fields**:
  1. Name - Company/Job name
  2. Location - Job location/city
  3. Department - Company department
  4. Work Type - Remote, On-site, Hybrid, etc.
  5. Package - Salary/compensation package
  6. Company Size - Number of employees
  7. Position Type - Full-time, Part-time, Contract, etc.
  8. Qualification - Required qualifications
- **UI Features**:
  - Scrollable form with white container
  - Professional input fields with borders
  - "Add Item" button with primary color styling

### **edit_screen.dart**

- **Purpose**: Form to edit existing job placement records
- **What it does**:
  - Pre-populates form fields with existing job data
  - Allows modification of all job details
  - Updates the job item in the list
  - Handles city list updates if location changes
  - Prevents duplicate city entries
  - Saves changes to persistent storage
- **Key Logic**:
  - Retrieves job by index from items list
  - Initializes TextEditingControllers with current values
  - Properly disposes controllers to prevent memory leaks
  - Checks for duplicate cities before adding new locations

### **fragment_holder.dart**

- **Purpose**: Navigation management and data models
- **What it does**:
  - Defines the HomeItem data model
  - Manages navigation between different screens (/Home, /Add, /Edit)
  - Handles data loading and saving via SharedPreferences
  - Maintains global data state (cities and data lists)
- **HomeItem Model**:
  - Properties: name, location, department, workType, package, companySize, positionType, qualification
  - Methods: `toJson()` for serialization, `fromJson()` for deserialization
- **Data Persistence Functions**:
  - **loadList()**: Loads saved job placements and cities from SharedPreferences on app startup
  - **savedList()**: Saves job placements and cities list to SharedPreferences after any CRUD operation
- **Navigation**:
  - Uses nested Navigator with route-based navigation
  - Routes: `/Home` (main list), `/Add` (create), `/Edit` (update)

## 🎨 Design & Colors

**Color Palette Used:**

- **Primary (kPrimary)**: `#093C5D` - Navy Blue (AppBar, buttons)
- **Secondary (kSecondary)**: `#3B7597` - Steel Blue (dropdown background)
- **Accent (kAccent)**: `#6FD1D7` - Light Blue (tags, borders)
- **Highlight (kHighlight)**: `#5DF8D8` - Cyan (important text, details)
- **White (kWhite)**: Card backgrounds and text

**UI/UX Elements:**

- Gradient backgrounds for visual appeal
- Rounded corners for modern look
- Emoji icons for visual categorization
- Cards with borders and shadows
- Responsive padding and spacing

## 🔧 Dependencies

The project uses the following Flutter packages:

```yaml
cupertino_icons: ^1.0.8 # iOS-style icons
flutter_svg: ^2.3.0 # SVG image support
google_fonts: ^8.1.0 # Google Fonts integration
image_picker: ^1.2.2 # Image selection
flutter_launcher_icons: ^0.14.4 # App icon generation
shared_preferences: ^2.5.5 # Local data persistence
```

## 💾 Data Storage

- **Technology**: SharedPreferences
- **Storage Keys**:
  - `My_Data`: JSON array of all job placement objects
  - `My_Cities`: JSON array of unique city names
- **Data Format**: JSON serialization/deserialization
- **Persistence**: Data persists across app sessions

## 🚀 Getting Started

### Prerequisites

- Flutter SDK 3.11.5 or higher
- Dart SDK (included with Flutter)

### Installation

1. Clone the repository
2. Navigate to the project directory
3. Run `flutter pub get` to install dependencies
4. Run `flutter run` to start the application

### Building

- **Android**: `flutter build apk`
- **iOS**: `flutter build ios`
- **Web**: `flutter build web`
- **Windows**: `flutter build windows`
- **macOS**: `flutter build macos`
- **Linux**: `flutter build linux`

## 🎮 Usage

1. **Launch App**: The splash screen appears for 3 seconds while loading data
2. **View Jobs**: Main page displays all job placements in scrollable list
3. **Filter by City**: Use the dropdown at the top to filter jobs by location
4. **Add Job**: Tap the '+' icon in AppBar to add a new placement
5. **Edit Job**: Click the edit icon on any card to modify details
6. **Delete Job**: Click the delete (trash) icon to remove a placement
7. **Data Saved**: All changes are automatically saved to local storage

## 📊 Workflow

```
SplashScreen (3s)
    ↓
loadList() → Fetch from SharedPreferences
    ↓
FragmentHolder (Navigation Hub)
    ├─ HomeScreen (View & Filter)
    │   ├─ Add Button → AddScreen
    │   ├─ Edit Button → EditScreen
    │   └─ Delete Button → Remove & Save
    ├─ AddScreen (Create)
    │   └─ Add Button → Save to List & Storage
    └─ EditScreen (Update)
        └─ Edit Button → Update List & Storage
```

## 🔄 Data Flow

**Add/Edit Operations:**

1. User fills form fields
2. New/Updated HomeItem object created
3. Item added/updated in items list
4. City added to cities list (if new)
5. `savedList()` called to persist data
6. Navigation returns to HomeScreen

**Delete Operation:**

1. User clicks delete icon
2. Item removed from items list
3. City removed from cities list
4. `savedList()` called to persist changes
5. UI updates with setState()

## 🔐 Data Model

```dart
HomeItem {
  String name;              // Company name
  String location;          // Job location
  String department;        // Company department
  String workType;          // Work arrangement type
  String package;           // Compensation package
  String companySize;       // Number of employees
  String positionType;      // Job type (FT/PT/Contract)
  String qualification;     // Required qualifications
}
```

## 📝 Development Notes

- The app uses a simple state management approach with setState
- No external state management library (Provider, Riverpod, etc.) is used
- Navigation is handled through named routes using nested Navigator
- All UI components use Flutter's built-in Material Design widgets
- Responsive design uses MediaQuery for adaptive layouts

## 🐛 Known Limitations

- No network/API integration (local storage only)
- No user authentication system
- No cloud synchronization
- Limited data validation on form inputs
- No image upload for companies

## 🚦 Future Enhancements

- Integration with job APIs (LinkedIn, Indeed, etc.)
- User authentication and profile management
- Cloud synchronization across devices
- Advanced filtering (salary range, experience level)
- Job application tracking
- Notifications for new opportunities
- Export to PDF/Excel
- Dark mode support
- Multi-language support

## 📄 License

This project is private and not publicly licensed.

## 📞 Support

For issues or feature requests, please contact the development team.
