# Does online anonymity do more harm than good — and is less of it even on the table?

*Status: open · last touched 2026-10-03 · sources checked 2026-10-03*

## The question

A video about VPNs set this off. The pitch in that genre is always the same — install this, become invisible — and what struck me was not whether the product delivers, but that I had no settled view on whether I wanted it to. Anonymity online is something I have always treated as a feature of the landscape rather than as something anyone chose, and when I tried to say whether it was good that we have it, I found I leaned one way without being able to say why.

So: **does online anonymity do more harm than good — and if we decided it did, could we actually have less of it?**

The second half is not a rhetorical flourish. Most of what gets said about anonymity assumes it is a setting someone could turn down, and that assumption deserves to be checked before the moral arithmetic starts, because an ethical argument about an option nobody has is a waste of everyone's time.

### Three rungs, routinely confused

"Anonymity" covers three different conditions, and a great many arguments about it are arguments in which each side has a different one in mind.

- **Pseudonymity.** I write as someone who is not my legal name, but the platform knows who I am — it has my phone number, my payment card, the addresses I connected from. The audience cannot identify me; a court order can. This is the condition most people are actually in when they think they are anonymous.
- **Platform-blind anonymity.** Nobody at the platform knows either: no account tied to anything that identifies me. But the network still records that this device spoke to that server at that moment, so the link exists for anyone able to observe both ends.
- **Network-blind anonymity.** Neither the platform nor an observer on the wire can connect the content to the person. This is what onion routing and mixnets are built for, and it is the only rung on which "anonymous" means what the word is usually taken to mean.

The rungs matter because the costs and the benefits are not distributed evenly across them. A troll needs only the first. A dissident under a government that can subpoena the platform needs the third. If the harms of anonymity concentrate on one rung and the benefits on another, then the question "should anonymity be available" has no single answer, and the interesting work is in locating the line rather than in defending either end of it.

### Three things anonymity is not

**Privacy** is about what is seen; anonymity is about who did it. I can be fully identified and still have my messages private, and I can be anonymous while everything I write is in the open — in fact that is the usual case, since the point of anonymous speech is that it be read.

**Encryption** protects content, not authorship. It hides what I said from everyone except the recipient, while leaving the fact that I said something to someone entirely visible. Metadata is the part that identifies, and encryption does not touch it.

**Impunity** is what anonymity gets accused of being, and it is not the same thing. Anonymity raises the price of finding out who acted; it does not repeal the rule that was broken, and it does not make the act undiscoverable. The distinction matters for the argument that follows, because "harder to prosecute" and "impossible to prosecute" support very different conclusions.

### My starting position

Written down before I went looking, so it can be seen afterwards whether it survived: **online anonymity is mildly bad.** Not catastrophic, not a thing I would tear out at any cost, but on balance a loss. Three reasons, in the order they occurred to me:

1. **It hides illegal activity, and that activity hurts innocent people.** This is the reason I hold most firmly. Whatever else anonymity does, it is the operating condition for markets and exchanges whose victims never consented to any of it.
2. **It enables the spread of disinformation.** Claims that would die under a name survive when nobody has to own them.
3. **It enables bot farms.** Inauthentic accounts at scale are possible because accounts need not correspond to people.

I am aware this is the common position rather than a worked-out one, which is the reason for writing the note rather than for trusting the position. What I want to know is which of those three reasons survives contact with the evidence, and whether what is left supports the conclusion I started with or a different one.

## Conjectures

- **A — Net harm.** The balance is negative. Anonymity is the operating condition for categories of harm whose victims are picked at random and never consented to anything: markets in material produced by abusing children, extortion operations that take hospitals offline, fraud run at industrial scale. Against that sit benefits that are real but diffuse, and largely enjoyed by people who had other options. A world with less anonymity online would be a better world — and the fact that this is also the intuitive position is not by itself an argument against it. *(This is my starting position, stated here in its strongest form rather than its most common one.)*
- **B — Shield of the weak.** Anonymity is the necessary condition for speech by people with something to lose: whistleblowers, dissidents, people reporting an abuser they live with, journalistic sources, anyone persecuted for an identity they cannot put down. Every mechanism that strips anonymity strips it from these people first, because they are the ones for whom being identified carries a cost. The harms are the price of there being any opposition to power at all.
- **C — Not a dial.** The question "should anonymity be available" is malformed, because anonymity is not a setting anyone controls. Either the technical possibility of network-blind communication exists — in which case it cannot be withdrawn from bad actors in particular — or it does not, in which case the people under threat do not have it either. There is no middle position on the dial. There is only the question of who holds the key.
- **D — The middle rung.** Most of the benefit comes from pseudonymity, where a person can still be found by due process, and most of the harm requires network-blind anonymity, where nobody can be found at all. The answer is therefore neither pole but a shift of one rung: let the name be optional, keep the trail.
- **E — Who holds the key.** The real question is not how much anonymity, but who may break it, on what grounds, and under whose supervision. Every proposal to end anonymity is in substance a proposal to hand someone a power, so the balance cannot be computed without knowing who that someone is and what restrains them.

## Refutations & tensions

The three reasons behind A do not hold up equally well, and the differences between them turned out to be the most informative thing in this note. I take them in the order I first thought of them, which is roughly the reverse of their strength.

### 1. Illegality: the firmest leg, and what it actually claims

The strong version of this leg is not that anonymity correlates with crime. It is that network-blind anonymity is the *operating condition* for particular markets — ransomware infrastructure that has to stay reachable while remaining unlocatable, and hosting for material produced by abusing children — and that the victims of those markets are selected at random and consent to nothing. Stated that way the leg does not depend on how much of the traffic on anonymity networks is criminal, a number that is notoriously contested, and it does not need anonymity to be the *cause* of the crime. It needs only that removing the anonymity would remove the market in its current form. That seems right to me, and nothing I read moved it.

What the evidence does unsettle is the step from there to "therefore anonymity defeats enforcement". The two largest darknet markets to be taken down were not reached by breaking the anonymity. Silk Road's server was located after a misconfiguration briefly exposed its IP address, and Ross Ulbricht was tied to it through a chain of ordinary operational mistakes: he had advertised the site under the handle `altoid` on public forums and then reused that handle to recruit developers, and the encryption key on the server carried the string `frosty@frosty`. AlphaBay fell further still from any technical break — its administrator's personal email address, `pimp_alex_91@hotmail.com`, had been sitting in the header of the welcome message the site sent every new user, and that address led to a PayPal account, to forums where he had posted under his own name, and from there to his real identity and his arrest in Bangkok in 2017.

So anonymity raised the price of the investigation without closing it. That is a weaker claim than the one usually made on this leg, and it cuts both ways: it means enforcement is possible, and it also means enforcement that succeeds does so by waiting for human error rather than by having a key. Both halves matter later, when E asks what a key would be worth.

### 2. Disinformation: the leg that shifted under me

Here the shape of my reason was wrong, and the sourcing corrected it in a way I did not expect — not by showing anonymity matters less, but by showing I had been imagining the wrong mechanism.

I had pictured disinformation as diffuse: a mass of unaccountable accounts, each contributing a little, with anonymity as the enabling condition for all of them. Grinberg and colleagues, looking at registered voters on Twitter during the 2016 US election, found engagement with fake news sources to be extraordinarily concentrated instead: "Only 1% of individuals accounted for 80% of fake news source exposures, and 0.1% accounted for nearly 80% of fake news sources shared." They also found that "for people across the political spectrum, most political news exposure still came from mainstream media outlets." A phenomenon driven by one account in a thousand is not a mass phenomenon, and a mass of anonymous accounts is not the mechanism.

There is also a well-measured channel for misinformation that is not anonymous at all. Mosleh and Rand built a tool for scoring Twitter users' exposure to misinformation from "elites" — public figures and organisations — using PolitiFact fact-checks to assign falsity scores to 816 of them, and found users' exposure scores negatively correlated with the quality of news those users then shared themselves. Every one of those 816 is a named, identifiable actor.

**What I must not claim here, and originally intended to.** I expected to write that the most effective disinformation travels under real names, because a name lends authority an anonymous account cannot borrow. Neither of these papers shows that. Grinberg measures concentration, not anonymity; Mosleh and Rand measure an elite channel without comparing it to an anonymous one. Neither abstract discusses anonymity at all. What the two together support is narrower: that disinformation is concentrated rather than diffuse, and that a large identified channel exists. Whether named sources outperform anonymous ones per unit of reach is a question I did not find answered, and it stays open rather than getting asserted.

Even so, the leg has moved. "Anonymity enables disinformation" was doing work in my position that it cannot do: whatever is driving a phenomenon concentrated in a tenth of a percent of users, it is not the general availability of anonymity.

### 3. Bot farms: the leg that inverted

This is the reason I would have defended most casually, and it is the one that turned out to be backwards. Inauthentic accounts at scale do not need anonymity. They need *identity* — and they buy it.

The infrastructure is a market with published prices. Roozenbeek, Dek and van der Linden tracked real-time pricing for the SMS verifications used to create fake accounts across more than 500 platforms over twelve months to July 2025, and the numbers are not deterrents: $0.08 per verification in Russia, $0.10 in the UK, $0.26 in the US, with per-platform averages of $0.08 for Meta, $0.10 for X and Instagram, $0.11 for TikTok and LinkedIn *(as of 2025-07)*. Open marketplaces sell Facebook accounts advertised as aged one to three years with phone and ID verification already completed, in bulk, at around $1.50 each *(as of 2026-10)*. The industrial end of the same business is larger still: Europol's Operation SIMCARTEL dismantled a network running SIM farms that had been used to create over 49 million fake accounts across more than 80 countries.

And where identity cannot be bought, it gets stolen. The Mueller indictment of the Internet Research Agency alleges its operatives used the Social Security numbers, home addresses and dates of birth of real US persons, without their knowledge, to open at least four bank accounts and six PayPal accounts, and charges four of them with aggravated identity theft. The accounts that carried the operation were not anonymous. They impersonated identifiable Americans, because impersonation is what bought the credibility the campaign needed.

The one qualification worth keeping, because it is also the most interesting finding for C and D below: price is not irrelevant. The same research reports that verification costs more where SIM cards cost more — $4.93 in Japan, $3.24 in Australia — and the authors' reading is that this "is likely to suppress rates of malicious online activity". Stricter identity requirements, on this evidence, do not prevent the abuse; they tax it. Whether a tax that large is worth having is a real question, and it is not the same question as whether anonymity should exist.

### Where that leaves A

One leg held, one moved, one inverted. The strongest form of my position is now narrower than the position I started with: it rests on network-blind anonymity being the operating condition for specific markets whose victims never consented, and it can no longer lean on disinformation or bot farms, because in those two the mechanism runs through identity — bought, stolen, or simply held by named elites — rather than through its absence. The honest summary of the shift is that anonymity makes some of what I objected to *cheaper*, and that it makes almost none of it *possible*.

### 4. How much harm, actually — and why the numbers will not come clean

Before the ethics, the size of the thing. This is where I expected to find a settled figure and found instead a cautionary tale about how such figures are made.

The number that circulates is that over 80% of requests to Tor hidden services go to abuse sites, from Owen and Savage's crawl of some 80,000 hidden services over six months. The Tor Project's response is the more instructive document. Hidden service traffic is about 1.5% of all Tor traffic, so the 80% was never 80% of Tor. And the measurement has a survivorship problem the authors acknowledge in their own framing: the graphs "only show data about the sites that were still up many months later: so his data could either show a lot of people visiting abuse-related hidden services, or it could simply show that abuse-related hidden services are more long-lived than others." Without knowing how many sites vanished before the crawl reached them, the denominator is unknown. The study's own authors did not undertake a formal legal classification at all.

The best-grounded estimate I found works from the user side rather than the request side. Jardine, Lindner and Owenson, using data from Tor entry nodes, estimate that on an average country/day about 6.7% of Tor users connect to hidden services that are disproportionately used for illicit purposes — which leaves the large majority of Tor use somewhere other than the part of the network the harms live in.

**And then the finding that cuts against where I was heading.** The same paper reports that the balance varies systematically with a country's political conditions, and not in the direction that flatters the liberal case: using Freedom House's classifications, illicit hidden-service use is *more* prevalent in "free" countries (~7.8%) than in "partially free" (~6.7%) or "not free" ones (~4.8%). The authors' own title says it: the potential harms of Tor cluster disproportionately in free countries. The reading is uncomfortable and I think it is correct. Anonymity's defensive value is highest where speech is punished, and its abuse value is highest where it is not — so for someone arguing about this from inside a democracy, the local balance is worse than the global one. B is a real argument, but it is an argument that mostly cashes out somewhere else, for someone else. That is a cost to my own conclusion, not to A's.

### 5. What a VPN actually does

This is where the video that started this gets its answer. A VPN does not remove traceability; it moves the trust. Without one, the party able to link my traffic to me is my internet provider. With one, it is the VPN operator — a company whose claim not to keep records is, from the outside, unfalsifiable marketing.

Two cases show what that exposure is worth. IPVanish advertised a zero-logs policy; after a 2016 Homeland Security summons to its parent company it initially said it had no user data, then on a follow-up request produced connection logs with the subject's real name, email address, originating IP and the times of each connection. In a 2017 FBI cyberstalking investigation PureVPN, also advertising no logs, supplied connection timestamps and originating addresses, and investigators described those records as the key to the identification.

So on the three rungs, a consumer VPN does not deliver network-blind anonymity and does not even reliably deliver platform-blind anonymity. It delivers pseudonymity with a single point of failure, and it relocates that point from a regulated utility to a company selected largely on the strength of its own advertising. For the hazards most buyers actually have in mind — a government, a serious adversary, a court order — the move is close to nil. Against an advertiser or an open Wi-Fi snoop it is real. The product is not a fraud; it is just sold against a threat model its buyers do not have.

### 6. Against C: the rungs exist, and the dial turns for the wrong people

C says there is no middle setting. The strong counterexample arrived while this note was being written, and it is worth more than any argument I could construct.

The UK's Online Safety Act took effect on 25 July 2025, requiring "highly effective age assurance" — facial age estimation, photo ID, credit card or bank checks — on services showing adult content. The response was immediate and measurable: Proton reported sustained daily UK sign-up increases of 1,400 to 1,800%, levels it compared to those it normally sees during civil unrest; NordVPN reported around 1,000%; half the top ten UK App Store downloads that day were VPN or identity apps. Because the obligation attaches to UK IP addresses, appearing to be elsewhere is sufficient, and Ofcom has conceded that VPNs cannot be blocked under the Act. A consultation in March 2026 asks whether activating a VPN should itself require age verification *(as of 2026-10)* — which is what the next rung down looks like when the previous one leaks.

So C is too strong as stated. Middle settings do exist, they are being legislated, and they have effects. But the effect they have is the one the verification market already demonstrated: identity requirements function as a **tax**, not a wall. Roozenbeek and colleagues found verification costs more where SIM cards cost more, and read that as likely to suppress rates of malicious activity — so the tax is not pointless. It is simply levied on whoever will not take two minutes to route around it. The curious adolescent pays it; the organised operation buys 49 million accounts wholesale and does not.

The accurate version of C is therefore narrower and, to me, more damning than the original: anonymity is a dial, but it turns almost exclusively for the people we were least worried about. Every notch costs the incidental user their privacy and the determined actor a rounding error.

## Where it stands

## Threads to pull

## Sources
