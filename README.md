# discord-ban-code
first of all thank you so much for downloading.
stop this discord ban command, good work in advance
The reason I gave this is that it is difficult to find on the internet, so I wanted to share with you the code that I wrote to help you.
 
code:
client.on('message', message => {
  if (!message.guild) return;
if (message.content.startsWith('-ban')) {
    if (!message.member.hasPermission('ADMINISTRATOR')) return message.channel.send('Bunu yapamazsın')
    const user = message.mentions.users.first();
    if (user) {
      const member = message.guild.member(user);
      if (member) {
        member
          .ban()
          .then(() => {
          const log = message.guild.channels.cache.find(channel => channel.name
 === 'log-kanalı')
           log.send(`${user.tag} kişisi banlanmıştır.`);
          })
          .catch(err => {
            message.reply('banlanmıştır');
            console.error(err);
          });
      } else {
        message.reply("Bahsettiğin kişi bizim sunucuda bulunmuyor");
      }
    } else {
      message.reply("Yasaklanacak kişiyi yazmadın.");
    }
  }
});

producer: Syrtejs
My GitHub profile: https://github.com/Syrtejs
