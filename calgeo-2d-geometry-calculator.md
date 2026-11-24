# Portfolio Project Data — Calgeo - 2D Geometry Calculator

- **Category:** `desktop-mobile` (`Mobile App`)
- **Category Label:** `Mobile App`
- **Accent Color:** `amber`
- **Target Assets Folder:** `public/images/projects/calgeo_2d_geometry_calculator/`
- **Required Local Images:** `banner.webp`, `image01.webp`

## TypeScript Data (`ProjectCaseStudy`)

```typescript
{
  "id": "calgeo-2d-geometry-calculator",
  "code": "PRO-07 // APP-03",
  "title": "Calgeo - 2D Geometry Calculator",
  "category": "desktop-mobile",
  "categoryLabel": "Mobile App",
  "year": "2022",
  "status": "Completed",
  "accentColor": "amber",
  "repoUrl": "https://github.com/weztcy/Calgeo-2D-Geometry-Calculator",
  "license": "MIT License",
  "banner": "/images/projects/calgeo_2d_geometry_calculator/banner.webp",
  "summary": "Offline native Android geometry calculator built in Java for fast area and perimeter computation across eight 2D shapes.",
  "projectDescription": "Calgeo is a native Android application written in Java with Material Design 3 that computes area, perimeter, and circumference for eight 2D shapes. Featuring dynamic per-shape input forms, numeric and triangle-inequality validation, and edge-to-edge layouts, it operates fully offline.",
  "architectureSummary": "Single-activity Jetpack Navigation host routing between HomeFragment, CalculatorFragment, and AboutFragment over static repository schemas and pure validation/calculation utilities.",
  "techStack": [
    "Java",
    "Android SDK",
    "AndroidX",
    "Material Design",
    "Jetpack Navigation",
    "ConstraintLayout",
    "RecyclerView",
    "ViewBinding",
    "Gradle",
    "JUnit",
    "Espresso"
  ],
  "telemetryMatrix": {
    "projectType": "Native Android Mobile Utility",
    "targetPlatform": "Android 8.0+ (API 26 to 36)",
    "primaryDomain": "2D Geometry Computation",
    "architecturePipeline": "Single-Activity Fragment Repository Flow",
    "testingAndAudit": "JUnit & Espresso Configured",
    "projectStatus": "Completed",
    "projectYear": "2022"
  },
  "desktopMobileProjectInfo": {
    "applicationType": "Native Android Mobile Utility",
    "targetPlatform": "Android (API 26+)",
    "developmentStatus": "Completed",
    "developmentYear": "2022",
    "applicationCategory": "Educational & Mathematical Utility"
  },
  "desktopMobileBackground": "Students, educators, and technical practitioners frequently need rapid area and perimeter calculations across varied 2D shapes without relying on internet connectivity or ad-heavy web calculators. Generic calculators require memorizing formulas, whereas dedicated offline utilities often lack proper geometric input validation.",
  "desktopMobileProblemStatements": [
    {
      "title": "Manual Formula Recall Overhead",
      "description": "Calculating area and perimeter across disparate shapes such as trapezoids, rhombuses, kites, and circles on standard calculators requires memorizing distinct parameter combinations.",
      "issueCode": "ISSUE_01"
    },
    {
      "title": "Invalid Geometric Input Propagation",
      "description": "Naive calculator forms fail to catch non-positive values, malformed decimals, or geometrically impossible triangle side lengths before executing arithmetic formulas.",
      "issueCode": "ISSUE_02"
    },
    {
      "title": "Connectivity Dependency in Utility Apps",
      "description": "Many lightweight calculation tools rely on web views or ad-supported network calls, causing unnecessary latency and failure in offline classroom or field environments.",
      "issueCode": "ISSUE_03"
    }
  ],
  "desktopMobileObjectives": [
    {
      "title": "Schema-Driven Dynamic Input Forms",
      "description": "Generate shape-specific decimal input fields dynamically from a centralized ShapeRepository mapping for all eight supported 2D shapes.",
      "targetTag": "TARGET_01"
    },
    {
      "title": "Deterministic Geometric Validation",
      "description": "Enforce positive finite numeric checks and the triangle inequality theorem in InputValidator prior to running GeometryCalculator formulas.",
      "targetTag": "TARGET_02"
    },
    {
      "title": "Zero-Dependency Offline Execution",
      "description": "Deliver an instant-launch native Android APK using Material Design 3, ViewBinding, and WindowInsets edge-to-edge support with zero network permissions.",
      "targetTag": "TARGET_03"
    }
  ],
  "desktopMobileFeatures": [
    {
      "title": "Eight-Shape Catalog & Dynamic Forms",
      "description": "Supports Square, Rectangle, Triangle, Circle, Parallelogram, Trapezoid, Rhombus, and Kite, dynamically inflating between one and five labeled decimal inputs per shape.",
      "badge": "CORE_MATH"
    },
    {
      "title": "Two-Stage Input & Triangle Validation",
      "description": "Validates required values, finite positive numbers, and triangle side inequalities (a + b > c) while highlighting invalid TextInputLayout fields and scrolling focus to the first error.",
      "badge": "VALIDATION"
    },
    {
      "title": "Contextual Result Presentation & Reset",
      "description": "Formats area and perimeter (switching label to circumference for Circle) to at most two decimal places inside a dedicated card, with smooth scroll-to-result and one-tap reset.",
      "badge": "UX_FLOW"
    },
    {
      "title": "Edge-to-Edge Window Insets & DayNight UI",
      "description": "Configures WindowCompat edge-to-edge rendering with dynamic status bar, navigation bar, and display cutout padding alongside Material 3 light and night color palettes.",
      "badge": "NATIVE_UI"
    }
  ],
  "desktopMobileInterfaceShowcase": [
    {
      "imageUrl": "/images/projects/calgeo_2d_geometry_calculator/image01.webp"
    }
  ],
  "desktopMobileUserFlow": {
    "summary": "Users start on a visual 2-column shape grid, select any of the eight 2D figures to load shape-specific input fields, enter positive decimal measurements, trigger validation and deterministic formula execution, and review formatted results or reset inputs instantly.",
    "steps": [
      {
        "step": "01",
        "title": "Shape Selection on Home Grid",
        "description": "User browses the 2-column RecyclerView grid in HomeFragment and taps a shape card, dispatching its ShapeType name via Jetpack Navigation Bundle arguments.",
        "actorOrNode": "User / HomeFragment"
      },
      {
        "step": "02",
        "title": "Dynamic Field Inflation",
        "description": "CalculatorFragment queries ShapeRepository for the selected ShapeType and inflates matching ItemInputFieldBinding rows with Next/Done IME keyboard actions.",
        "actorOrNode": "CalculatorFragment / ShapeRepository"
      },
      {
        "step": "03",
        "title": "Validation & Soft-Keyboard Dismissal",
        "description": "Tapping Calculate clears active focus, hides the soft keyboard via InputMethodManager, and runs InputValidator across per-field and triangle-inequality rules.",
        "actorOrNode": "UI Thread / InputValidator"
      },
      {
        "step": "04",
        "title": "Formula Evaluation & Result Scroll",
        "description": "GeometryCalculator computes area and perimeter into an immutable CalculationResult, formatted via Locale-aware NumberFormat and smoothly scrolled into view.",
        "actorOrNode": "GeometryCalculator / UI Thread"
      }
    ]
  },
  "desktopMobileArchitecture": {
    "summary": "Calgeo follows a single-activity, multi-fragment Android architecture driven by Jetpack Navigation and ViewBinding. Presentation fragments delegate static schema lookup to ShapeRepository, input verification to InputValidator, and mathematical computation to GeometryCalculator.",
    "layers": [
      {
        "name": "Navigation & Window Host Layer",
        "role": "Configures edge-to-edge WindowInsets padding and hosts NavHostFragment for type-safe fragment transitions.",
        "tech": "AndroidX & Jetpack Navigation",
        "components": ["MainActivity", "nav_graph.xml", "ActivityMainBinding"]
      },
      {
        "name": "Presentation & Adapter Layer",
        "role": "Renders Material Design 3 screens, 2-column shape grid cards, dynamic input rows, and formatted calculation results.",
        "tech": "Material Design & ViewBinding",
        "components": ["HomeFragment", "CalculatorFragment", "AboutFragment", "ShapeAdapter"]
      },
      {
        "name": "Static Catalog & Domain Model Layer",
        "role": "Provides immutable definitions of supported 2D shapes, input schemas, and calculation result value objects.",
        "tech": "Java",
        "components": ["ShapeRepository", "Shape", "ShapeType", "InputField", "CalculationResult"]
      },
      {
        "name": "Validation & Computation Engine",
        "role": "Executes deterministic numeric parsing, triangle inequality checks, and area/perimeter mathematical formulas.",
        "tech": "Java",
        "components": ["InputValidator", "GeometryCalculator"]
      }
    ]
  },
  "desktopMobileDataManagement": {
    "storageType": "In-Memory Static Repository",
    "stateEngine": "Fragment ViewBinding & Navigation Arguments",
    "offlineSyncStrategy": "100% Offline Local Computation",
    "cachingMechanism": "Unmodifiable Static Lists & Drawable Resource IDs"
  },
  "desktopMobilePlatformImplementation": [
    {
      "title": "Edge-to-Edge System Bar & Cutout Insets",
      "description": "MainActivity calls WindowCompat.setDecorFitsSystemWindows(false) and applies WindowInsetsCompat systemBars and displayCutout padding globally without consuming insets for child fragments.",
      "badge": "SYSTEM_UI"
    },
    {
      "title": "IME Keyboard Flow & Focus Management",
      "description": "CalculatorFragment assigns IME_ACTION_NEXT to intermediate decimal fields and IME_ACTION_DONE to the final field, hiding the soft keyboard via InputMethodManager on Done, Calculate, or background tap.",
      "badge": "INPUT_IME"
    },
    {
      "title": "Gradle Version Catalog & ViewBinding Build",
      "description": "Configured with Android Gradle Plugin, Java 17 source/target compatibility, Material 3 DayNight themes, and ViewBinding enabled across all activity, fragment, and item layouts.",
      "badge": "ANDROID_BUILD"
    }
  ],
  "desktopMobileTechSpecs": {
    "programmingLanguage": "Java",
    "framework": "Android SDK & Material Design",
    "localStorage": "In-Memory Repository"
  },
  "desktopMobilePlatformSpecs": {
    "targetPlatform": "Android 8.0+ Devices",
    "packageFormat": "Android APK Bundle",
    "targetArchitecture": "Universal Android ABI",
    "buildFootprint": "Lightweight Offline Native APK"
  }
}
```
