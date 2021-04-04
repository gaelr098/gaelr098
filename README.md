- 👋 Hi, I’m @gaelr098
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
gaelr098/gaelr098 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
@shuhiko const Discord = require (discord.js);

const {

 MessageEmbed

} = exiger (discord.js);

const config = require (../../ botconfig / config.json);

const ee = require (../../ botconfig / embed.json);

const emoji = require (../../ botconfig / emojis.json);

const playermanager = require (../../ handlers / playermanager);

module.exports = {

 nom: jouer,

 catégorie: 🎶 Musique,

 alias: [p],

 description: Lit une chanson à partir de YouTube,

 utilisation: jouer <Song / URL>,

 run: async (client, message, args, cmduser, texte, préfixe) => {

 essayer {

 // récupère l'instance du canal

 const {

 canal

 } = message.member.voice;

 // sinon dans une erreur de retour de canal vocal

 si (! canal)

 return message.channel.send (nouveau MessageEmbed ()

 .setColor (ee.wrongcolor)

 .setFooter (ee.footertext, ee.footericon)

 .setTitle ($ {emoji.msg.ERROR} Erreur | Vous devez rejoindre un canal vocal.)

 );

 // si aucun argument ne renvoie une erreur

 si (! args [0])

 return message.channel.send (nouveau MessageEmbed ()

 .setColor (ee.wrongcolor)

 .setFooter (ee.footertext, ee.footericon)

 .setTitle ($ {emoji.msg.ERROR} Erreur | Vous devez me donner une URL ou un terme de recherche.)

 );

 // récupère l'instance du joueur

 const player = client.manager.players.get (message.guild.id);

 // f pas dans le même canal -> retour

 if (player && channel.id! == player.voiceChannel)

 return message.channel.send (nouveau MessageEmbed ()

 .setColor (ee.wrongcolor)

 .setFooter (ee.footertext, ee.footericon)

 .setTitle ($ {emoji.msg.ERROR} Erreur | Vous devez être dans mon canal vocal pour utiliser cette commande!)

 .setDescription (Channelname: \ $ {message.guild.channels.cache.get (player.voiceChannel) .name} `)

 );

 // joue le morceau de YOUTUBE

 playermanager (client, message, arguments, chanson: youtube`);

 } catch (e) {

console.log (chaîne (e.stack) .bgRed)

 return message.channel.send(new MessageEmb
