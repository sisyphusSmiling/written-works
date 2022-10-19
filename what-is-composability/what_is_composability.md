![spongebob revealing composability in a rainbow meme](./images/spongebob_composability.jpeg)
## Composability Will Deliver the Web We Were Promised
> And Why You Should Be Building on Flow

Allow me to introduce you to the tech world’s next biggest buzzword…[composability](https://en.wikipedia.org/wiki/Composability). As a Smart Contract Engineer on Flow, I can tell you it’s not just any buzzword, though. Composability is the focus of some of the [most](https://youtu.be/vOQYcx7G1rQ) [influential](https://a16z.com/2018/12/16/4-eras-of-blockchain-computing-degrees-of-composability/) VC’s, it’s the talk of the entirety of World Wide Web 3.0, and rightfully so.

We’ll explore exactly what composability is, why it’s important, I’ll give you a couple examples, then we’ll cover the necessary components to support development of composable systems, and you’ll get some resources for further reading — it’ll be a good time. Let’s dive in.

So wtf is composability, you ask? Put simply, it’s the ability for a component to be used as a building block. [Chris Dixon](https://twitter.com/cdixon/status/1451703070589587456) put it nicely when he tweeted that “composability is the ability to mix and match software components like lego bricks”.

**Resource Composability**

Composability isn’t a new concept, and it can be applied to a variety of different contexts. There’s [community composability](https://future.com/can-community-composability-help-web2-users-make-the-jump-to-web3/) between DAOs, the [financial composability](https://boxmining.com/defi-money-legos/) of DeFi, data composability á la [Ceramic](https://developers.ceramic.network/learn/features/); the list goes on.

I’ll add to that list the concept of resource composability. [Resources](https://developers.flow.com/cadence/language/resources) in Cadence, the smart contract language powering the Flow blockchain, “are types that can only exist in one location at a time and must be used exactly once.” Once created, any time you load a resource, it must be saved or destroyed. If this sounds familiar, it should — it’s no different than objects in meatspace. My car might look like other cars, but it’s unique and has only ever existed in one place at a time from the day it was created.

There’s certainly [more to resources](https://medium.com/dapperlabs/resource-oriented-programming-bee4d69c8f8e), and we’ll get into them a bit later. The important takeaway is that resources dovetail naturally with composability. In resources, the shape and uniqueness of a digital object are inherent to it. A resource can be defined such that it can be utilized for purposes other than that for which it was originally designed, a building block if you will. Additionally, once you have a resource, no one can take it away from you, giving you total ownership over the asset and how you decide to use it.

### What exactly is composability?

Before we dive into what composability is, let’s consider some things that are not composable. We see non-composable designs every day - a laptop manufacturer uses a proprietary screw head, an iPhone requires a lighting connector, an airline mileage program issues non-transferable airline miles.

A composable world is one in which each of these components are not only interoperable with other systems, but useful to some other end entirely. Of course that laptop manufacturer could have used a phillips head, that iPhone probably could have implemented USB-C, and those airline miles likely could be transferable. If that were the case, those same objects could have been used in a variety of contexts, making them composable. Whether they should be composable in a business sense is another question. From the perspective of cumulative engineering hours, dollars, and physical resources spent to manifest widgets in the world, composability is the most efficient and interoperable.

> Composability leads to less redundancy, increasing efficiency of resources and interoperability
> 

### Composable == Lunchables

Let’s take a walk from the office to the kitchen for a second. Imagine you’re about to prep some food for yourself to eat over the next few days.

The non-composable method would be to prep each meal and divvy them up into separate containers. You’ll still end up with food, but that’s not only a lot work up front, it’s also inflexible. The output is singular — your meals are exactly what you put in those containers and nothing else.

Alternatively, you want to mix up your meals throughout the week. Instead of prepping a bunch of complete chicken and rice bowls, maybe you prep some chicken breast, a bean and corn salad, and some rice. Monday you can build yourself a bowl, but Tuesday you could add a tortilla and grill up a warm burrito. Maybe you add some shredded chicken to your morning egg scramble and top it with that bean and corn salad.

Or your roommate could take that chicken and mix it up with their barbecue sauce and burger buns to make a spicy chicken sandwich. You get greater flexibility, and your roommate could use something you already made as a building block for their own creation.

If you chose the second approach, congrats, you’re a composable thinker (or perhaps a bit indecisive)!

> Planning for composability is thinking about what you are building in terms of its constituent components and compartmentalizing the base functionality of each of those in a manner that makes them useful as a building block to something else.
> 

To paraphrase Dieter Shirley, Dapper Labs CTO, building a product with composability in mind is to move from monolithic-product to diverse-platform thinking. Unlike walled-garden products, open platforms have compounding effects, allowing for quicker adoption and greater breadth of use cases than the original creators could have imagined. When you build a composable system, others can not only use the components you built as you intended, but they can take them — individually or in parts — to build something entirely new, benefiting everyone utilizing those components with greater diversity.

### Composability on-chain

Okay, so we know composability gets us more efficiently built and interoperable systems, but wtf do blockchains have to do with this?

Before I answer this, I’ll assume you have at least enough familiarity with blockchain systems to know that they’re shared infrastructure. Meaning that when you perform some action in a blockchain network, your actions are computed and results shared across all machines powering the network. So if I write up and deploy a smart contract, anyone on the network can see that code, meaning anyone could use that code.

Why does this matter? Well, if anyone can use that code, I can build it in such a way that others can use the logic or, more importantly, the resources defined within it. If you’re at all familiar with software development, you might think of libraries. But libraries don’t really get to the core of composability. The composability I’m talking about is incredibly more powerful than the bundles of functionality provided by libraries. The power of composability in the context of blockchains, Flow in particular, is witnessed by leveraging extensible resources as building blocks on the shared infrastructure of the chain.

DeFi is a great example of the power of composable architectures, even garnering itself the term “money legos”. Regardless of the sector’s financial performance over the past year, the construction of DeFi systems as discrete and shared components that plug together to create new financial protocols is unlike anything we’ve ever seen.

Take a look at the latest version of the NFT Storefront contract on Flow for a concrete example of resource composability. Built for use with any standard NFT implementation, the [NFTStorefrontV2](https://github.com/onflow/nft-storefront/blob/main/contracts/NFTStorefrontV2.cdc) smart contract enables any account on Flow to create and save a storefront where they can list their NFTs for sale. It has built-in incentives for third party marketplace apps to propagate any listings and find a buyer without having to deploy any of their own code and all while the NFT remains in the lister’s account. This means any new NFT released on Flow has a built in peer-to-peer marketplace whether that NFT represents digital art, a song, or an in-game asset. Everyone in the ecosystem can reap the benefits from the existence of this single contract because every account can easily become a storefront.

### A bold future

I’ll leave you with a vision to be continued in later writings. Imagine a world — a maximally composable world — where you can pick up a game on your phone and play with a friend who’s playing on their laptop. You can choose your own custom game client with art from your favorite game animator. The in-game assets you earn and use throughout the game can be displayed on your social media account with full confidence that it’s actually yours — it sits in your account. You can list it for sale using that storefront contract I just mentioned, or use it in another game that just came out that accepts that same in-game asset.

It’s a world where the difficult logic of a game can be separated from the artistically creative frontend work of crafting animated gaming experiences for any device. Consider the implications such a world would have for platform interoperability, composability of all sorts of weird leaderboards, collectibility of game assets, creative open source community-supported game clients, and more. It incorporates the construction of a game as a part of the play. That’s why resource composability matters, because it enables people to work together to create new and novel things, significantly reducing overhead to implementation while increasing the impact of those new creations.

While such a world is technically possible with current technologies, integrations such as those described require a ton of permissions. Additionally, the assets you “own” from the in-game points to the game assets you earn are merely entries in a central suite of servers. Currently, game developers need to commit to a platform and design everything from the logic to the game assets to the in-game animations and more. Abstracting the logic to a smart contract creates a distinct and transparent layer of separation, opening up the core game functionality to any frontend that might want to interact with it to facilitate a game experience. On-chain visibility also allows for public querying of game state and previous game history of players and assets so leaderboards manifest effortlessly.

### Primordial soup of composability

In the decentralized world of Web 3.0 development, composability allows for increasingly complex order to emerge from chaos, with disparately developed primitives serving as single-celled organisms from which whole kingdoms of dApps will evolve. But an ecosystem must contain certain attributes for these self-ordering and composable properties to emerge.

True [resource composability](https://medium.com/dapperlabs/resource-oriented-programming-bee4d69c8f8e) is fully realized when everyone shares the same infrastructure and the digital assets you use are quite literally owned by you — meaning they’re sitting in your account and only you can access, use or destroy them - not the creator or the infrastructure provider or anyone else; only you as the owner. 

Cadence’s unique resource-orientated paradigm in conjunction with the [multi-node architecture](https://flow.com/primer#primer-multinode) of the Flow blockchain allows for exactly such a representation of digital assets. That is, digital resources can only exist in one place within a single shared state among everyone on the network. That last part is critical to composability. Imagine trying to build a puzzle with your friends if everyone has a different picture of the available puzzle pieces and the current state of the puzzle. To work together across a distributed computer, it’s critical that everyone agrees on the state of all of its constituent components.

Fundamentally, a blockchain should contain the following to support the development of composable systems:

1. Unique and singleton representation of components and [resources](https://developers.flow.com/cadence/language/resources). Asset ledgers are great for accounting, but not so great for representing uniqueness and enforcing the single existence of a digital object.
2. [Mechanisms to mediate access to those resources](https://developers.flow.com/cadence/language/capability-based-access-control), ideally in a manner that spreads the attack surface area such that the blast radius of hacks is minimized. Users won’t be too enthused about their composable resources if it takes the hack of a single contract to lose them all.
3. [Agreement across the chain on the state of those resources](https://flow.com/primer#primer-multinode). If we’re all sharing the building blocks, we should probably agree on their shape before trying to stack them together.
4. Permissionless interoperability between components. In addition to access-control, builders and users need to safely and easily access components, resources and services across the shared ecosystem in order to utilize them as a part of something else.

To that list, I would also add:

1. Scalability to support platform growth. Compound trajectories are hardly beneficial if they exceed the scalability of the infrastructure you’re building on. This is a hard lessoned learned by the OG Flow team who had a hand in the enormous growth of Crypto Kitties.
2. A wide variety of custodial models among accounts to support user interactions with on-chain resources.

As you probably guessed by now, Flow is ideally suited to meet each of these needs for a variety of reasons. That’s for another article soon to come. Until then, be sure to level up your Cadence skills in the [Developer Portal](https://developers.flow.com/learn) and/or [Emerald Academy](https://academy.ecdao.org/) so you can code along with the upcoming tutorial where you’ll be walked you through a composable approach to building your own on-chain game unlike any other out there.

---

First time hearing about [Flow](https://flow.com/)? Check out the [Primer](https://flow.com/primer#primer-intro) and join the Flow [Discord](https://discord.com/invite/J6fFnh2xx6)!