# Portfolio Hub

🎓 A collaborative class portfolio platform where students can create, showcase, and manage professional profile cards in real time.

![Class Portfolio Screenshot](https://placehold.co/800x450/e2e8f0/64748b?text=Class%20Portfolio%20UI)

## Project Overview

Portfolio Hub is a single-page web application designed to help a class present their talent in one shared space.  
Each student can add a personal profile card with their bio and professional links, while all users see updates instantly through Firebase Firestore real-time listeners.

## Features

- Real-time profile updates for all users
- Responsive grid of student portfolio cards
- Detailed modal view for each profile
- Profile creation form with name, tagline, bio, and links
- Owner-only profile deletion with confirmation step
- Client-side sorting by creation date for stable display order
- Tailwind CSS based modern and mobile-friendly UI
- Toast notifications for user feedback

## Tech Stack

- **Frontend:** HTML5, CSS3, JavaScript (ES Modules)
- **Styling:** Tailwind CSS
- **Backend/Data:** Firebase Firestore + Firebase Authentication (anonymous/custom token)
- **Fonts:** Google Fonts (Inter)

## Setup and Run

This project is currently implemented as a single `index.html` file and can be opened directly in a browser.

### Local Preview

1. Clone the repository.
2. Open `index.html` in your browser.

### Firebase-Enabled Usage

The application expects runtime Firebase values (for example `__firebase_config`, `__app_id`, and optional `__initial_auth_token`) to be injected by the host environment.  
If these are not available, the app uses demo placeholders and cannot connect to a real Firestore instance.

## How It Works

1. Initializes Firebase app/auth/firestore on load
2. Authenticates user (custom token or anonymous)
3. Subscribes to Firestore collection updates via `onSnapshot`
4. Renders cards and modal details dynamically
5. Allows only profile owners to delete their own entries

## Repository Structure

```text
Portfolio_Hub/
├── index.html
├── README.md
├── LICENSE
├── .gitignore
└── CONTRIBUTING.md
```

## License

This project is licensed under the [MIT License](LICENSE).
