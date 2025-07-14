# Calista AI Search Interface

## Overview

This is a Flask-based web application that recreates and enhances the Calista AI search interface with a modern, vibrant design. The application features an animated dark-themed UI with glassmorphism effects, gradient animations, collapsible sidebar navigation, interactive search functionality, and colorful action buttons for different types of AI-powered operations like health analysis, content summarization, and data analysis.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Changes

**Date**: July 10, 2025
- Changed main content area to plain gray background with enhanced gradient overlays
- Implemented layout transformation system with two states:
  - **Initial State**: Centered search interface with vibrant action buttons
  - **Results State**: Chat-style layout matching reference image with tabs, response area, and follow-up input
- Enhanced sidebar design with gray theme while maintaining vibrant accent colors:
  - Added gradient icon backgrounds for visual appeal
  - Implemented glow effects and enhanced hover states
  - Added visual feedback for all navigation interactions
  - Created active state indicators with gradient accents
- Improved button functionality and visual feedback:
  - All navigation buttons now provide visual feedback and proper functionality
  - Action buttons include pulse glow effects and scale animations
  - Search interface buttons have tooltips and click handlers
  - Added proper button states (hover, active, loading)
- Added floating particle elements for "alive" feel
- Enhanced animations and micro-interactions throughout interface
- Maintained gray color palette while strategically using vibrant gradients for key interactive elements

## System Architecture

### Frontend Architecture
- **Technology**: HTML5, CSS3, JavaScript (Vanilla JS)
- **Styling**: Tailwind CSS with custom dark theme configuration
- **UI Framework**: Custom component-based design with responsive layout
- **Icons**: Font Awesome for consistent iconography
- **Fonts**: Inter font family for modern typography

### Backend Architecture
- **Framework**: Flask (Python web framework)
- **Structure**: Modular design with separate files for app initialization and routes
- **Session Management**: Flask sessions with configurable secret key
- **Environment Configuration**: Environment variables for production settings

### Template System
- **Engine**: Jinja2 (Flask's default templating engine)
- **Structure**: Base template with block inheritance for consistent layout
- **Responsive Design**: Mobile-first approach with Tailwind CSS utilities

## Key Components

### 1. Application Entry Point (`app.py`)
- Flask app initialization with debug logging
- Environment-based configuration for session secrets
- Circular import prevention through delayed route imports

### 2. Route Handler (`routes.py`)
- **Main Route** (`/`): Serves the primary search interface
- **Search Route** (`/search`): Handles POST requests for search queries
- **Action Routes** (`/action/<action_type>`): Manages different AI action types (health, summarize, analyze, plan, local)

### 3. Frontend Interface
- **Collapsible Sidebar Navigation**: Expandable sidebar (80px collapsed, 288px expanded) with gradient icon backgrounds and smooth animations
- **Search Interface**: Glassmorphism search bar with gradient elements, backdrop blur effects, and interactive icons
- **Vibrant Action Buttons**: Color-coded action buttons with gradient backgrounds, hover animations, and vertical card layout
- **Responsive Layout**: Mobile-optimized flexbox layout with adaptive sizing and animations
- **Interactive Elements**: Mouse trail particles, floating animations, typewriter effects, and scale transformations

### 4. Styling System
- **Modern Dark Theme**: Deep space background with gradient overlays and animated aurora effects
- **Glassmorphism Design**: Backdrop blur effects, transparent surfaces, and subtle borders
- **Gradient Animations**: Animated gradients on text, backgrounds, and interactive elements
- **Micro-interactions**: Hover effects, scale transformations, floating particles, and smooth transitions
- **Color Palette**: Purple (#8B5CF6), Cyan (#06B6D4), Amber (#F59E0B) gradients with dynamic animations

## Data Flow

1. **User Interaction**: User enters search query or clicks action buttons
2. **Frontend Processing**: JavaScript handles form submission and user interactions
3. **Backend Processing**: Flask routes process requests and return JSON responses
4. **Response Handling**: Frontend receives JSON responses and provides user feedback

## External Dependencies

### Frontend Dependencies
- **Tailwind CSS**: Utility-first CSS framework loaded via CDN
- **Font Awesome**: Icon library for consistent UI elements
- **Google Fonts**: Inter font family for typography

### Backend Dependencies
- **Flask**: Core web framework
- **Python Standard Library**: os, logging modules for configuration and debugging

## Deployment Strategy

### Development Environment
- **Host**: 0.0.0.0 (accessible from all interfaces)
- **Port**: 5000
- **Debug Mode**: Enabled for development
- **Logging**: DEBUG level for comprehensive error tracking

### Production Considerations
- Environment-based secret key configuration
- Debug mode should be disabled
- Static file serving optimization needed
- Database integration points prepared for future expansion

### File Structure
```
├── app.py                 # Flask application initialization
├── main.py               # Application entry point
├── routes.py             # Route definitions and handlers
├── templates/
│   ├── base.html         # Base template with common layout
│   └── index.html        # Main search interface template
└── static/
    ├── css/
    │   └── style.css     # Custom styling and component classes
    └── js/
        └── main.js       # Frontend JavaScript functionality
```

### Key Architectural Decisions

1. **Modular Structure**: Separated concerns between app initialization, routing, and templates for maintainability
2. **Template Inheritance**: Used base template pattern for consistent layout and easy maintenance
3. **JSON API**: RESTful approach with JSON responses for future API expansion
4. **Progressive Enhancement**: Basic functionality works without JavaScript, enhanced with JS
5. **Environment Configuration**: Prepared for production deployment with environment variables
6. **Static Asset Management**: Organized static files for efficient serving and caching

The application is designed to be easily extensible, with clear separation of concerns and preparation for future AI service integrations.