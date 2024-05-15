# Flutter Messaging

## Installation

### Setup firebase

- Firebase flutter project setup: https://rogue-bakery-576.notion.site/Firebase-InstallationCreate-Firebase-Account-94c0644c4bce44d894538545bbaf2104

## Notification Setup

### Use Firebase Cloud Messaging to get a token for the device.
Send this token to your server to target specific devices for notifications.
Creating a Notification Campaign:

Go to the Firebase console and create a new campaign for notifications.
Craft your notification message and target your Android device.
You can schedule notifications or send them right away.
Handling Received Notifications:

Implement a function to handle incoming notifications.
Use a Navigator key to navigate to a specific page when a notification is tapped.
Displaying Notification Content:

Retrieve the notification message, title, body, and data.
Display this information on a dedicated notification page in your app.