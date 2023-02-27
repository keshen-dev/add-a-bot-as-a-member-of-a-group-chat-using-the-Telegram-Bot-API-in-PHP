# add a bot as a member of a group chat using the Telegram Bot API in PHP

To add a bot as a member of a group chat using the Telegram Bot API in PHP, you can use the addChatMember method. Here is an example of how you can do it:

```
<?php
// Your bot token
$bot_token = "YOUR_BOT_TOKEN";

// Chat ID of the group where you want to add the bot
$chat_id = "GROUP_CHAT_ID";

// URL of the Telegram Bot API
$url = "https://api.telegram.org/bot$bot_token/addChatMember";

// Parameters for the API request
$params = [
    'chat_id' => $chat_id,
    'user_id' => "BOT_USER_ID"
];

// Send the API request to add the bot to the group chat
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_POSTFIELDS, $params);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
 

// Check if the API request was successful
if ($response) {
    echo "Bot added to group chat!";
} else {
    echo "Error adding bot to group chat.";
}
?>
```
