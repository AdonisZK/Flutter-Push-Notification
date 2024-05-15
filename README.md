![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/11268880-ba74-4404-8685-fe5b2afdde8a)![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/13d9778c-4b29-45a2-a5e3-b4fcd69ae199)# Flutter Messaging

## Installation

### Setup firebase

- Firebase flutter project setup: https://rogue-bakery-576.notion.site/Firebase-InstallationCreate-Firebase-Account-94c0644c4bce44d894538545bbaf2104

## Notification Setup

### Use Firebase Cloud Messaging to get a token for the device.
- Send this token to your server to target specific devices for notifications.
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/b7a88ca1-655b-48ad-a0bc-2af9945704f6)

### Creating a Notification Campaign:
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/9f23165c-82d5-4582-a9ac-2e7f7c530d55)
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/1839fe34-2ddb-4d94-bdf1-1b05e9639f6f)

### Go to the Firebase console and create a new campaign for notifications.
- Craft your notification message and target your device(s).
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/eb31a750-7004-4530-b4e1-6b7dbaf4777b)

### Handling Received Notifications:
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/09bb3ad6-697b-4f4a-a62a-b3cdf770efe9)
- Implement a function to handle incoming notifications.
- Use a Navigator key to navigate to a specific page when a notification is tapped.
```python
  void handleMessage(RemoteMessage? message) {
    if (message == null) return;

    navigatorKey.currentState?.pushNamed(
      '/notification_screen',
      arguments: message,
    );
  }
```
### Displaying Notification Content:
- Retrieve the notification message, title, body, and data.
- ![image](https://github.com/AdonisZK/Flutter-Push-Notification/assets/48209612/15014769-d135-405b-965d-e57b9e2e09ec)
```python
  Widget build(BuildContext context) {
    final message = ModalRoute.of(context)!.settings.arguments as RemoteMessage;

    return Scaffold(
      appBar: AppBar(title: Text("Notification")),
      body: Column(
        children: [
          Text(message.notification!.title.toString()),
          Text(message.notification!.body.toString()),
          Text(message.data.toString()),
        ],
      ),
    );
```
