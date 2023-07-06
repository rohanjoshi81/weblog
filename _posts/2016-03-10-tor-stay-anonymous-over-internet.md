---
title: "Tor : Stay Anonymous over Internet"
date: 2016-03-10T12:00:00+05:30
categories:
  - blog
tags:
  - learning
  - tech
---

Tired of ads following you wherever you go on the internet ? How to escape from the various website trackers and cookie traps?

What’s on your mind ? Well if you said “Private browsing” , then don’t be surprised to know that you are wrong. When you use any web browser your search history ,cache and cookies ,etc are stored by the browser you use,but in private browsing mode the browser does not stores these information . This allows a person to browse the Web without storing local data that could be retrieved at a later date. While the computer won’t have a record of your browsing history, your internet service provider or employer can still track the pages you visit.

Tor – otherwise known as The Onion Network – is an effort to anonymize your Web browsing , originally designed and implemented by the U.S. Navy , for the primary purpose of protecting government communications. Today, it is used every day for a wide variety of purposes by normal people, the military, journalists, law enforcement officers, activists, and many others.The Onion Router (TOR) is a project application designed to encrypt the traffic going out of your computer so that anyone watching your connection would not see what you are doing, instead they will see lines of encrypted information – Keeping your activity anonymous.

Using Tor protects you against a common form of Internet surveillance known as “traffic analysis.” Traffic analysis can be used to infer who is talking to whom over a public network. Knowing the source and destination of your Internet traffic allows others to track your behavior and interests.

TOR is basically built on the concept of onion routing.In onion routing, packets are sent through a network of randomly selected proxy servers before being delivered to their final destination.The idea of onion routing is to protect the privacy of the sender and recipient of a message, while also providing protection for message content as it traverses a network. The original messages are repeatedly encrypted and then they are sent through several network nodes called onion routers.It is exactly like the structure of Onion,to reach to the original message you have to peal off (i.e decryption is applied) the outer upper layers one after another,the message is in the core,each onion router removes a layer of encryption to uncover routing instructions and sends the message to the next router where this is repeated. This prevents these intermediary nodes from knowing the origin, destination, and contents of the message.

Is it 100% secure ?

The answer is NO , though the message is encrypted during the transmission but ,the last intermediate exit node still has complete access to the encrypted message and can unwrap the encrypted message received from the node just before it , thus revealing the content. Your original content can still be protected if you have an end to end encryption for the message sent, then the exit nodes cannot read the information just like any other encrypted link over the internet.

You need to change some of of your browsing habit with TOR browser to protect your identity

- Don’t Use torrent over internet : It has been observed that Torrent file-sharing applications ignore proxy settings and make direct connections even when they are told to use Tor.Even if your torrent application connects only through Tor, you will often send out your real IP address in the tracker GET request, thus revealing your identity.

- Don’t Enable or install browser plugins : The Tor Browser blocks browser plugins as they can be manipulated to reveal your IP address. It is also recommend not to install additional addons or plugins into the Tor Browser, as these may bypass Tor or otherwise harm your anonymity and privacy.

- Use HTTPS versions of websites : Tor encrypts your traffic to and within the Tor network, but the encryption of your traffic to the final destination website depends upon on the website you visit. To help ensure private encryption to websites, the Tor Browser Bundle includes HTTPS everywhere to force the use of HTTPS encryption. However, you should still watch the browser’s URL bar to ensure that it  includes “https://” in the URL, and display the proper expected name for the website.

How to use Tor as an end user ?

Well you can simply use a browsers which provides Tor feature. However, if you don't want 'secret agent' level of anonymity simply using a browser like Brave or Firefox Focus which blocks trackers is enough and is quite faster.