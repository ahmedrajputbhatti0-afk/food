# Smart Complaint Center – Presentation Guide

## 1. Project Introduction
Smart Complaint Center is a frontend-only website where people can submit complaints about public services (electricity, water, gas, internet, education, healthcare, roads), receive a unique complaint ID, and track the status. It is built with plain HTML, CSS and JavaScript.

**Honest limitation:** complaints are saved only in *this browser's* localStorage. They are NOT sent to any real office or server, and other users/browsers cannot see them. The contact form is also a demo: no email is sent. A real system would need a backend and database.

## 2. Objectives
- Practise HTML, CSS and JavaScript without frameworks.
- Build a working form with validation.
- Store and retrieve data using localStorage.
- Generate unique IDs and search records.
- Create a responsive, professional interface.

## 3. Technologies Used
HTML5, CSS3 (variables, flexbox, grid, media queries), JavaScript (ES6), browser localStorage.

## 4. Explanation of the Files
- **index.html** – structure: header, home, statistics, forms, tracking, categories, contact, footer.
- **style.css** – design: colour variables (dark blue, white, grey), card styles, hover effects, grid layouts, responsive media queries, smooth scrolling.
- **script.js** – behaviour: validation, saving, ID generation, tracking, statistics, category-card clicks, mobile menu.

## 5. How Submission and Tracking Work
**Submission:** form submit → `preventDefault()` → `validateComplaint()` checks every field → build an object (id, name, category, subject, priority, status "Submitted", date) → push into the array from localStorage → `JSON.stringify` and save → show ID → reset form → `updateStats()`.

**ID generation:** find the highest existing number and add 1 (CMP1001, CMP1002 …), so IDs never repeat.

**Tracking:** read the array → loop to find a matching ID → show details, or "No complaint found. Please check your complaint ID."

**Statistics:** loop through saved complaints and count each status.

## 6. Demonstration Steps
1. Open `index.html`; show Home and the 3 info cards. Stats read 0.
2. Click nav links to show smooth scrolling.
3. Click the "Electricity" category card – it scrolls to the form with Electricity selected.
4. Click Submit with empty fields – show the error messages.
5. Fill in valid data and submit – note the ID (e.g. CMP1001); stats update; form clears.
6. Refresh the page – stats remain (localStorage).
7. In Track Complaint, enter the ID – show details. Enter a wrong ID – show the not-found message. Click Clear.
8. Open the Contact form, submit – show the demo-only message.
9. Resize the window to show the mobile layout and menu.
10. (Optional) F12 → Application → Local Storage → show the saved "complaints" data.

*Note:* the status stays "Submitted" because there is no admin panel. To demo other statuses, edit the status value in DevTools Local Storage to "In Progress" or "Resolved" and refresh to see the stats change.

## 7. Viva Questions
1. **What is localStorage?** A browser feature that saves small key-value data on the user's computer; it stays after refresh.
2. **Why JSON.stringify / JSON.parse?** localStorage stores only text, so arrays/objects are converted to text and back.
3. **How do you make IDs unique?** Find the highest existing number and add 1.
4. **Why is it not a real complaint system?** There is no server or database; data is only in one browser and not sent to any department.
5. **How is the design responsive?** CSS grid/flexbox and media queries change the layout for tablets and phones.
