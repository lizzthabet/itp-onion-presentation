---
marp: true
theme: gaia
paginate: true
backgroundColor: #dfe2e9
color: #343333
---
<style>
  :root {
    font-size: 18px;
  }

  section {
    font-family: monospace;
  }

  h1, h2, h3, h4 {
    font-weight: normal;
  }

  h4 {
    text-decoration: underline;
    font-size: 1rem;
  }

  section.small {
    font-size: 1rem;
  }
/* Add the word `scoped` to style tag for page-specific styles */
</style>

<!-- _class: default -->

# Let's peel an onion! 🧅
## A short introduction to Tor, from one beginner to another
### Lizz Thabet (she/they)
- [lizz.website](https://lizz.website)
- [github/lizzthabet](https://github.com/lizzthabet)

<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />

The slides: https://github.com/lizzthabet/itp-onion-presentation
The demo code: https://github.com/lizzthabet/itp-onion-demo

---
<!-- header: 🧅 An introduction to Tor -->
<!-- _footer: There are onion jokes down here 🕵🏻‍♂️ -->

# Demo checklist

We're going to make our version of the "share one thing!" show with onion sites, using our own computers as web servers. You'll need:

- A browser that can access the Tor network, like [Tor Browser](https://www.torproject.org/download/) (recommended) or [Brave Browser](https://brave.com/)

- A copy of the [demo repository](https://github.com/lizzthabet/itp-onion-demo)

There will be two demo options: one more beginner and one more intermediate. If you're comfortable running terminal commands and navigating the command line, try the intermediate demo.

*For the beginner demo, you'll need:*
- [OnionShare](https://onionshare.org/) ([onion link](http://lldan5gahapx5k7iafb3s4ikijc4ni7gx5iywdflkba5y2ezyg6sjgyd.onion/#download))

*For the intermediate demo, you'll need:*
- The `tor` binary that will let you run an onion service locally. See [installation instructions](https://community.torproject.org/onion-services/setup/install/) ([onion link](http://xmrhfasfg5suueegrnc4gsgyi2tyclcy5oz7f5drnrodmdtob6t2ioyd.onion/onion-services/setup/install/index.html)) for each OS.
- A way to run a web server locally, like python or nginx

---

<!-- _footer: What do you say to a small onion that has helped you? Thanks shallot. -->

# What we'll do today

Tor is a free and open source software for (more) anonymous communication.

## Goals
- Pique your curiosity about networking and the internet
- Demystify how Tor works and make it less scary... and even exciting!
- Pitch onion sites (and decentralized / p2p options) as a way to share your work

<!-- Speaker notes:
  ### What this session is not...
  - a guide to privacy and security best practices (with and without Tor)
  - historical overview of Tor (and its U.S. military funding)
  - ethical debates about free speech and Tor

  ...though there are many interesting and important spaces where these conversations are happening.
-->

## Outline

- Demo checklist ✅
- Define our goals ✅
- Review common terms and why you'd use Tor
- Break down the Tor ecosystem
- Overview of the Internet (as we know it) works
- The Tor network
- The magic of onion sites
- Share One Thing! onion site demo
- Further resources

<!-- 
  We're all experts! Feel free to chime in. If you ask me a question I can't answer, I'll look it up later and post the answer.

  If there's time:

    Why am I leading this session?

    I learned about Tor because I was building a browser-based tool (aka a website) and I wanted to distribute it through technology that was structurally more relational than having a Hosted Website.

    What power dynamics are structurally embedded in the internet as I know it? How might the technology of networks be more relational? How might I more actively participate as a viewer and co-creater in the internet?
-->

---

<!-- _footer: I just saw an onion ring ... so I answered it. -->

# Let's define some terms

But first, let's define some general terms and concepts.

In a **client-server model** of networking, the client is the device that sends a request for data to the server through a network, and the server is the device that accepts the request and delivers the requested data packets to the client.

<!-- TODO: If time, add p2p and decentralized definitions -->

The client and server communicate in an agreed-upon language called a **protocol**. (Examples of protocols you'll hear about include TCP, HTTP, and HTTPS.)

Each device on a network has a unique **IP address**, which is like a mailing address, that can identify and locate that device.

A **proxy** is another server that acts as an intermediary between clients and servers. A forward proxy (that forwards a request) is also called a tunnel or a gateway.

<!-- Extra notes:
  With HTTPS, the data that the client sends with its request to the server is encrypted, so only the client and the server can read it.
-->

---

<!-- _footer: What do you call an edible ion? An onion. -->

# Why use Tor?

When you use the Tor network, your internet service provider (ISP) won't be able to track the names and addresses of the websites you visit, instead they'll only see you're connecting to the Tor network. And the websites you visit will see a connection coming from the Tor network instead of your real IP address.

There are many reasons why someone might use Tor, including:
- To obscure your information from third-party data collection and tracking
- To access content where it might be censored
- To share content privately, securely, and anonymously
- To use more decentralized networks, where there isn't a central authority that determines what content is acceptable or not, and where the infrastructure is shared, rather than controlled by for-profit entity

... and other reasons!

There are also many caveats and limitations to using Tor, which are important to understand based on your needs.

<!-- 
  From The Tor Project:
  The primary goal of Tor is to improve your privacy by sending your traffic through a series of proxies. It aims to solve three privacy concerns:

  - First, Tor prevents websites and other services from learning your location, which they can use to build databases about your habits and interests.
  - Second, Tor prevents people watching your traffic locally (such as your ISP or someone with access to your home wifi or router) from learning what information you're fetching and where you're fetching it from. It also stops them from deciding what you're allowed to learn and publish.
  - Third, Tor routes your connection through more than one Tor relay so no single relay can learn what you're up to. Because these relays are run by different individuals or organizations, distributing trust provides more security than the old one hop proxy approach.
-->

---

<!-- _footer: I just saw an onion ring ... so I answered it. -->

# What is Tor?

The term `Tor` can be used to reference several different things. Let's break that down.

## 🌐 The onion network (The Tor circuit)
A network of virtual tunnels that allow you to improve your privacy and security on the Internet. I'll generally use "Tor" to refer to this virtual + physical infrastructure of servers and how a client's request for content is routed to its destination.

## 🔗 Onion sites
Websites that are only accessible over the Tor network.

## 🖥 The Tor browser
A version of Firefox that uses the Tor network to access the Internet and onion sites. It makes other privacy improvements, like preventing websites "fingerprinting" your device. By default, it doesn't keep any browsing history and cookies are only valid for a single session.

## 👥 The Tor Project
The 501(c)(3) nonprofit organization that develops free and open source Tor software.

<!-- Both the Tor network and onion sites are run through core `tor` or little-t Tor. -->
<!-- 
  Their stated mission is:
  > To advance human rights and freedoms by creating and deploying free and open source anonymity and privacy technologies, supporting their unrestricted availability and use, and furthering their scientific and popular understanding.
-->

---

# Overview of the Internet (as we know it)

We're going to borrow from [this wonderful guide](https://catnip.article19.org/data/ARTICLE19-Catnip-Tor-Network-2021-web.pdf) from 🌈 Catnip Explains 🌈.

![width:850px](./images/catnip-01-internet.png)

<!--
  Ask people if they'd like to review how the Internet works! This slide could be skipped depending on time and everyone's knowledge.

  In particular, your local ISP is in the position to build a complete profile of your Internet usage. In addition, every server in the Internet that can see any of the packets can profile your behavior.

  Excerpted from here:  http://rzuwtpc4wb3xdzrj3yeajsvm3fkq4vbeubm2tdxaqruzzzgs5dwemlad.onion/index.html#protections
-->

---

<!-- _footer: A botanist visited an onion farm and said to the farmer: "I'm sorry but I think your ground is leeking." -->

# So what does Tor do differently?

![width:1100px](./images/catnip-03-relay-network.png)

<!-- From Catnip guide:
  Any computer can run the Tor software and become a node. Think of Tor nodes like data checkpoints which take in, treat, and ship out packets traveling over the Tor network.
  
  Using Tor, data packets are sent over the Internet’s infrastructure like any other packet. But packets traveling through the Tor network are routed randomly through three nodes (also called relays or hops) before reaching their final destination.
  
  This route, called Tor circuit, is changed every ten minutes to make it harder to observe for potential eavesdroppers. To route the packets down a random path, they are packed like an onion: each is wrapped into three encrypted layers containing a dedicated packet tag. But only a partial route is encoded on these tags, so that none of the relays know the entire path a packet takes. At each relay a single layer is peeled off and the packet is then sent to the next relay written on the tag of the underlying layer. This unwrapping and preparing to relay the packets is managed by the Tor software of the node. 
  
  All that is visible from the outside is that obscure cargo is sent from place to place. Because of this, the Tor network is often pejoratively called the “dark net”. When we say that Tor packet layers are encrypted, it means that only the relay with the correct private encryption key is able to unwrap the corresponding layer.

-->

---

<!-- _footer: An opinion without 3.14 is ... just an onion. -->

# So what does Tor do differently?

![width:1125px](./images/https-onion-routing.png)

<!-- From The Tor Project:
  Tor works by sending your traffic through three random servers (which are called `relays`) in the Tor network. The first relay in the circuit is called a guard relay, and the last relay (called the exit relay) then sends traffic out onto the public internet. 

  There are three layers of encryption, one per node, so each relay only knows where the next location that it's sending the request. (Like a relay race!) Relays are run by volunteers throughout the world (so there's distributed trust) and they have IP addresses that are listed publically.

  *FAQ from the Tor Project*
  Q: What attacks remain against onion routing?

  A: As mentioned above, it is possible for an observer who can view both you and either the destination website or your Tor exit node to correlate timings of your traffic as it enters the Tor network and also as it exits. Tor does not defend against such a threat model.

  In a more limited sense, note that if a censor or law enforcement agency has the ability to obtain specific observation of parts of the network, it is possible for them to verify a suspicion that you talk regularly to your friend by observing traffic at both ends and correlating the timing of only that traffic. Again, this is only useful to verify that parties already suspected of communicating with one another are doing so. In most countries, the suspicion required to obtain a warrant already carries more weight than timing correlation would provide.

  Furthermore, since Tor reuses circuits for multiple TCP connections, it is possible to associate non anonymous and anonymous traffic at a given exit node, so be careful about what applications you run concurrently over Tor. Perhaps even run separate Tor clients for these applications.
-->

---

<!-- _footer: Where do you find an old Onion article? In their archives. -->

# That's cool! So how do onion sites fit in?

An onion site is a website that's only accessible over the Tor network. The communication between a client and a server never leave the Tor network, so both the client and server can remain anonymous. An onion site's IP address is never made available to the requesting client.

The technology and content of onion sites are decentralized, so there isn't a central authority that determines what content is accessible and what isn't.

When you create an onion site, you get a `hostname`, a public key, and a private key, all of which are used to encrypt communications and communicate with the Tor network.

There's a more [detailed breakdown](https://torproject.org/onion-services/overview/index.html) ([onion link](http://xmrhfasfg5suueegrnc4gsgyi2tyclcy5oz7f5drnrodmdtob6t2ioyd.onion/onion-services/overview/index.html)) on The Tor Project.

<!--
  Onion sites are also great for network health and sustainability, bc they don't add to the traffic on exit nodes, where there can be bottlenecks. When a user visits a particular onion, they know that the content they are seeing can only come from that particular onion. (No man-in-the-middle DNS attacks are possible.)

  Onion mirrors (NYTimes, Markup, Facebook, Twitter) also make sure that sites are accessible where they might be censored.

   TODO: Add a note about p2p uses!
 -->

---

<!-- _footer: What kind of chips do you eat in the bath? Shower cream and onion. -->

![width:950px](./images/onion-service-combined-05-09.png)

---

<!-- _footer: Why does Mr. Potato Head have a mobile? In case Mr. Onion rings. -->

# ✨🧅🌐 Demo 🔗👥🎨
<br />
<br />

## Let's head over to Github for the instructions! https://github.com/lizzthabet/itp-onion-demo

---

<!-- _footer: What do you call an onion that won’t hold water? A leek. -->
# An extremely non-exhaustive list of additional resources

[Tech Learning Collective](https://techlearningcollective.com/): Technology education for radical organizers and revolutionary communities

[Metro's Decentralized Web series](https://metro.org/decentralizedweb)

[Beaker Browser](https://beakerbrowser.com/): Experimental p2p browser


## Specific to onion sites
- [How to make any site an onion site](https://github.com/alecmuffett/eotk)
- [In-depth technical overview of onion sites](https://community.torproject.org/onion-services/)
- [Best practices for onion sites](https://riseup.net/en/security/network-security/tor/onionservices-best-practices)
- [Evaluate your onion site's vulnerabilities with Onionscan](https://github.com/s-rah/onionscan)

---

# Terms that may be helpful

**Client-server model**: In the client-server architecture, when the client computer sends a request for data to the server through a network, the server accepts the requested process and delivers the requested data packets to the client. 

**Decentralized network**: A decentralized network is not dependent on a single set of servers run by one company or entity. Federated and peer-to-peer networks are different approaches to designing networks that structurally empower users.

**Peer-to-peer (p2p) network**: In a p2p netwrok, each user's computer functions as both a client and a server, both requesting data and responding to requests. Each computer acts as equals or "peers," enabling people to communicate directly with each other.

**Federated network**: In a federated network, computers still function in a "client-server" model, where your computer is requesting data stored on someone else's server. The difference is that virtually anyone can run a server that connects and operates with other servers in the network. In general, there may be more trust between you and the servers that you're interacting with than between you and a for-profit corporation.

---
# I've heard of *x*. Is it like Tor?

**VPN (Virtual Private Network)**: a tool that creates a secure "tunnel" between a device and a VPN provider that conceals a device's IP address and encrypts traffic between the device and the VPN so that it can't be observed or intercepted on a local network. (The Tor Project has a [long guide](http://eweiibe6tdjsdprb4px6rqrzzcsi22m4koia44kc5pcjr7nec2rlxyad.onion/legacy/trac/-/wikis/doc/TorPlusVPN) to using a VPN with Tor.)

**BitTorrent**: a file-sharing protocol that makes it easier and faster to share very large files over a network. It's decentralized and peer-to-peer. (Note: The Tor Project has a lengthy blog post on torrenting files through Tor and how many torrent applications expose identifying user data.)

Anything else?