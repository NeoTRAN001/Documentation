## ¿Qué es ZeroNet?

ZeroNet utiliza la criptografía de Bitcoin y la tecnología de BitTorrent para construir una **red descentralizada resistente a la censura**. 

Los usuarios pueden publicar sitios estáticos o dinámicos en ZeroNet y los visitantes pueden elegir si quieren o no distribuir el sitio ellos mismos. Los sitios web permanecerán en línea mientras un par siga en línea.

Cuando un sitio es actualizado por su propietario, todos los nodos que distribuyen ese sitio (visitantes anteriores) recibirán solamente las actualizaciones realizadas en el contenido del sitio.

ZeroNet se distribuye con una base de datos SQL lista para usar. Esto facilita el desarrollo de sitios con mucho contenido. Luego, la base de datos se sincroniza con los nodos de alojamiento a través de actualizaciones incrementales. 


## ¿Por qué? 

* Creemos en la comunicación abierta, gratuita y sin censura. 
* Sin censura: después de que se publica algo, no hay forma de eliminarlo. 
* No hay un solo punto de falla: el contenido permanece en línea incluso si solo un par lo distribuye. 
* Imposible de parar: no está en ninguna parte porque está en todas partes. El contenido es distribuido por cualquier usuario que desee contribuir.
* Rápido: ZeroNet utiliza la tecnología BitTorrent para entregar contenido más rápido que los servidores centralizados.
* Trabajar sin conexión: Puede acceder al sitio incluso si su Internet no está disponible.
* Seguro: La propiedad del contenido está asegurada utilizando la misma criptografía que protege su billetera Bitcoin. 

[comment]: <> (I'm unsure about the following bit. Thoughts?)
[comment]: <> (# What problem is ZeroNet solving?)

[comment]: <> (When Tim Berners-Lee created the internet, he meant for it to be free. Not surveilled nor censored. And [he is still fighting for that](http://edition.cnn.com/2014/03/12/tech/web/tim-berners-lee-web-freedom/).)

[comment]: <> (The internet is centralized mainly in two places: Content and Domain Names (URLs) are hosted and controlled by central servers. If you control the central servers (and if you are powerful enough you do) you control the network.)

[comment]: <> (**Decentralized content storage**)

[comment]: <> (ZeroNet tackles the content storage problem by giving everyone the ability to store content. Site visitors can choose to store a website on their computers, and when they do this they also help to serve the site to other users. The site is online even if only one user is hosting it.)

[comment]: <> (**Shared DNS cache**)

[comment]: <> (Site addresses on ZeroNet are cached by all network members. When you type a ZeroNet site URL on your browser this will query other peers connected to you about the site. If one of these peers happen to have the site they will send it to you, if not, they will forward your query along.)

[comment]: <> (This architecture means that when a site URL is created, as long as one peer is serving it, there is no way to take the URL down.)


## Features
 * Easy, zero configuration setup.
 * Password-less [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki)
   based authorization: Your account is protected by the same cryptography as your Bitcoin wallet.
 * Sites updated in real-time, no refreshing needed.
 * Namecoin .bit domains support.
 * SQL Database support: Allows for easier site development and faster page load times.
 * Anonymity: Full Tor network support with .onion hidden services instead of ipv4 addresses.
 * TLS encrypted connections.
 * Automatic, uPnP port opening.
 * Plugin for multiuser (openproxy) support.
 * Works with any browser/OS.


## How does it work?

* After you install and run ZeroNet, you open a site by visiting:
  `http://127.0.0.1:43110/{zeronet_site_address}`
  (e.g.  `http://127.0.0.1:43110/1HeLLo4uzjaLetFx6NH3PMwFP3qbRbTf3D`).
* ZeroNet will then use the BitTorrent network to find peers that are seeding the site and will download the site content (HTML, CSS, JS...) from these peers.
* Each site visited is then served by your client. Sites can be removed or blacklisted if necessary.
* Every site contains a list of all of its files, each entry containing a SHA512 hash and a signature generated using the site owner's private key.
* If the site owner modifies the site, then he/she signs a new list and publishes it to the peers.
  After the peers have verified the files list integrity (using the
  signature), they download the modified files and publish the new content to
  other peers.

##### [Slideshow about ZeroNet cryptography, content updates, multi-user sites &raquo;](https://docs.google.com/presentation/d/1_2qK1IuOKJ51pgBvllZ9Yu7Au2l551t3XBgyTSvilew/pub?start=false&loop=false&delayms=3000)


## Screenshots

![Screenshot](./img/zerohello.png)

![ZeroTalk](./img/zerotalk.png)

##### [More screenshots &raquo;](using_zeronet/sample_sites/)

## Current limitations

* <strike>No torrent-like, file splitting for big file support</strike> (BigFile plugin enables this)
* File transactions are not compressed <strike>or encrypted yet</strike> (TLS encryption added)
* No private sites

## Help to keep this project alive

Bitcoin: 1QDhxQ6PraUZa21ET5fYUCPgdrwBomnFgX

[Full donation page](help_zeronet/donate/)

### Thank you!

* More info, help, changelog, zeronet sites: [http://www.reddit.com/r/zeronet/](http://www.reddit.com/r/zeronet/)
* Come, chat with us: [#zeronet @ FreeNode](https://kiwiirc.com/client/irc.freenode.net/zeronet) or on [gitter](https://gitter.im/HelloZeroNet/ZeroNet)
