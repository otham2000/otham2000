const TelegramBot = require('node-telegram-bot-api');
'6392347443:AAHjKq8jCnLEmPbKzuXybseoCnEHQhc782Q';
// Create a new bot instance
const bot = new TelegramBot(botToken, { polling: true });
// Handle /start command
bot.onText(/\/start/, (msg) =>
{const chatId = msg.chat.id;
  const message = 'Welcome to the cefr_master! How can I assist you?';
  bot.sendMessage(chatId, message);
});

// Handle student registration button
bot.on('callback_query', (query) => {
  const chatId = query.message.chat.id;
  const message = 'Please fill out the student registration form: ...';
  bot.sendMessage(chatId, message);
});

// Handle job vacancy application button
bot.on('callback_query', (query) => {
  const chatId = query.message.chat.id;
  const message = 'Please provide your details to apply for the job vacancy: ...';

  bot.sendMessage(chatId, message);
})
// Handle useful information button
bot.on('callback_query', (query) => {
  const chatId = query.message.chat.id;
  const message = 'Here is some useful information: ...';
l
  bot.sendMessage(chatId, message);
});
// Start the bot
bot.on('polling_error', (err) => console.error(err))
