# Portfolio_Hub

# 🎓 Class Portfolio Showcase

A dynamic, single-page web application that serves as a collaborative portfolio for an entire class. It allows students to easily add, view, and manage their professional profiles in a shared, real-time environment.

![Class Portfolio Screenshot](https://placehold.co/800x450/e2e8f0/64748b?text=Class%20Portfolio%20UI)

---

## ✨ Features

-   **Real-Time Collaboration**: Built with **Firebase Firestore**, the portfolio updates instantly for all users. When a new student adds their profile, it appears on everyone's screen without needing a page refresh.
-   **Dynamic Profile Cards**: Students can create a personal profile card featuring:
    -   Profile Picture (via URL)
    -   Full Name and a professional tagline.
    -   A detailed bio.
    -   Links to their Portfolio, LinkedIn, and GitHub.
-   **Interactive UI**: The main page displays a clean, responsive grid of all student profiles. Clicking on any card opens a detailed modal view with more information.
-   **Add & Manage Profiles**: An elegant, collapsible form allows students to easily add their own profiles.
-   **Secure Deletion**: Students can only delete the profiles they created, ensuring data integrity. A confirmation step is included to prevent accidental deletions.
-   **Consistent Ordering**: Profiles are consistently sorted by their creation date, providing a stable and predictable layout.
-   **Modern Styling**: Styled with **Tailwind CSS** for a sleek, mobile-first design that looks great on all devices.
-   **User Feedback**: Non-intrusive toast notifications provide clear feedback for actions like adding or removing a profile.

---

## 🛠️ Tech Stack

-   **Frontend**: HTML5, CSS3, JavaScript (ES Modules)
-   **Styling**: [Tailwind CSS](https://tailwindcss.com/)
-   **Backend & Database**: [Google Firebase](https://firebase.google.com/)
    -   **Firestore**: For the real-time NoSQL database.
    -   **Firebase Authentication**: For anonymous user management.
-   **Fonts**: [Google Fonts](https://fonts.google.com/) (Inter)

---

## 🚀 How It Works

The application is a single `index.html` file that contains all the necessary HTML, CSS, and JavaScript.

1.  **Initialization**: On page load, the app initializes a connection to Firebase.
2.  **Authentication**: It authenticates the user anonymously to get a unique user ID (`uid`) required for secure write/delete operations.
3.  **Data Fetching**: The app fetches all student profiles from the Firestore database.
4.  **Real-Time Updates**: An `onSnapshot` listener is attached to the collection. This listener automatically detects any changes (additions, modifications, deletions) in the database and updates the UI in real-time.
5.  **Adding a Profile**: When a user submits the form, a new document is created in the Firestore collection. This document includes the student's information and their unique `creatorId` (their Firebase `uid`).
6.  **Deleting a Profile**: In the detailed modal view, a "Remove Profile" button appears *only* if the current user's `uid` matches the profile's `creatorId`. This ensures only the owner can delete their own card.
7.  **Client-Side Sorting**: To ensure a consistent and stable order, the fetched profiles are sorted by their `createdAt` timestamp directly in the browser before being rendered.
