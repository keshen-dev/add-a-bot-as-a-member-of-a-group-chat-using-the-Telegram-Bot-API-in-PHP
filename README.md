# add a bot as a member of a group chat using the Telegram Bot API in PHP

To add a bot as a member of a group chat using the Telegram Bot API in PHP, you can use the addChatMember method. Here is an example of how you can do it:

```
<?php
// Your bot token
$bot_token = "YOUR_BOT_TOKEN";

// Chat ID of the group where you want to add the bot
$chat_id = "GROUP_CHAT_ID";

// URL of the Telegram Bot API
$url = "https://api.telegram.org/bot$bot_token/";

// Parameters for the API request
$params = [
    'chat_id' => $chat_id,
    'user_id' => "BOT_USER_ID"
];

// Send the API request to add the bot to the group chat
$result = file_get_contents($url . "addChatMember?" . http_build_query($params));

// Check if the API request was successful
if ($result) {
    echo "Bot added to group chat!";
} else {
    echo "Error adding bot to group chat.";
}
?>
```
