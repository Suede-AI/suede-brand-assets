<!-- MULTI-PLATFORM ESSAY — ready for Medium, Substack, Hashnode, Dev.to, LinkedIn Article -->
TITLE: Detection Is Not Ownership
SUBTITLE: C2PA credentials and acoustic watermarks answer "is this AI?" Nobody built the layer that answers "whose is this?"
TAGS: AI, Intellectual Property, Music Industry, Creator Economy, Provenance

AUTHOR: Jason Colapietro (also publishing as Johnny Suede)
CROSSPOST: suedeai.ai · guitar.solutions

---

# Detection Is Not Ownership

This morning, a courtroom in Munich ruled on whether an AI music company needed permission to train on copyrighted songs. Whichever way you first heard the outcome framed, the case itself proved something nobody disputes anymore: the era of unaccountable generation is closing.

And the industry has an answer ready. Provenance metadata. Content Credentials. Watermarks.

Suno embeds C2PA manifests in every exported track. So does Udio. ElevenLabs ships Content Credentials in its music output. Spotify has reportedly removed tens of millions of AI tracks. Deezer scans every daily upload through automated watermark and fingerprint detection. The tooling is real, it mostly works, and the press releases write themselves: the provenance problem is being solved.

It isn't. Because the systems being deployed answer a different question than the one creators need answered.

Every watermark, manifest, and fingerprint in production today is built to answer: **is this AI, and which model made it?**

Nobody's royalty routes through the answer. No licensing deal executes off it. No court settles a claim with it. Detection is a policing question. Ownership is a property question. The industry is building world-class infrastructure for the first and calling it a solution to the second.

Those are different things.

---

## What the provenance stack actually does

It helps to be precise about the two layers, because they fail in opposite directions.

**Layer one is the C2PA manifest** — a cryptographically signed block of metadata attached to the file. It records who made the content, with what tool, and whether AI was involved. The signature means tampering is detectable: alter the manifest and the math breaks.

But the signature only protects a manifest that is *present*. Strip the whole block — transcode the audio, re-encode it, pass it through a converter — and nothing breaks, because there's nothing left to break. The file plays fine. A missing manifest raises no alarm, because billions of legitimate files have no manifest either. The cryptography is excellent and it is bolted to the one part of the file that doesn't survive contact with the real world.

**Layer two is the acoustic watermark** — a signal woven into the audio itself. This one is genuinely hard to remove. It survives format conversion, re-encoding, speed changes. Platform-side detection reads it at upload and knows which model generated the track.

Here's what almost nobody says out loud: the durable layer doesn't serve the creator. An acoustic watermark identifies the *generator* — it says "Suno made this" or "this came from Udio's model." It exists so platforms can enforce their AI policies and so model vendors can recognize their own output. It does not say who prompted it, who owns it, what rights attach to it, or where the money should go. The creator does not appear in the signal at all.

So the layer that's easy to strip is the one that names you. The layer that survives names the machine.

---

## A label is not a proof

There's a distinction I keep coming back to, because the entire watermarking conversation collapses without it.

**A label travels with cooperation. A proof survives hostility.**

The label on a jacket tells you who made it — as long as nobody cuts it out. The moment someone has a reason to remove it, it's gone, and the jacket doesn't tattle. Labels work in cooperative systems, where every handler agrees to preserve them.

The creative economy is not a cooperative system. It is an adversarial one. The person who wants to use your work without paying you is precisely the person who will transcode the file. Metadata that depends on the goodwill of everyone downstream is not protection. It's decoration.

A proof is different. A proof doesn't ride inside the asset, hoping to arrive intact. A proof is a record that exists *independently* of any copy of the file — timestamped, verifiable, and still standing after every copy has been stripped, re-encoded, renamed, and reposted. You don't ask the file who owns it. You ask the record.

Deeds work this way. Nobody staples the title to the house. The house can burn down and the ownership survives, because ownership was never stored in the asset. It was stored in a registry.

C2PA is a label. Ownership needs a deed.

---

## What the registry has to do

Strip the metaphors away and the requirements are concrete. An ownership layer that actually functions has to do four things no watermark does:

- **Record the claim at creation** — who made this, when, from what — anchored somewhere that doesn't depend on any single copy of the file surviving intact.
- **Bind identity to the work**, not the tool to the work. "Generated by model X" is trivia. "Owned by creator Y, under terms Z" is an asset.
- **Stay queryable by anyone** — platforms, licensees, courts, and increasingly software agents that need a machine-readable answer to "can I license this, from whom, at what price?" before they transact.
- **Connect to consequences.** A registry that can't route a payment or execute a license is a museum. The claim, the terms, and the settlement have to live in one system, or the gaps between systems become the place where creators lose.

Run today's provenance stack against that list. C2PA records the claim but stores it in the most fragile place available. Acoustic watermarks are durable but bind the wrong party. Neither is queryable as a rights source. Neither routes a dollar. Four requirements; the deployed stack meets zero of them.

That's not a criticism of the engineers — detection was the problem platforms needed solved, so detection got built. It's a criticism of mistaking it for the whole job. Twelve months of watermark deployments have produced the strange spectacle of an industry declaring the provenance problem handled while no deployed system can answer the only question a royalty statement cares about.

---

## Why courtrooms can't build it

Which brings me back to Munich.

GEMA's case against Suno — like Universal and Sony's cases in the U.S., grinding toward 2027 — asks courts to decide whether training on protected music requires permission. These rulings matter enormously. They set the liability. They shift leverage in every licensing negotiation on both continents.

But follow the logic of any pro-rightsholder outcome one step past the headline. If AI companies must license what they train on, they need to know — at training time, at catalog scale — who owns every work and under what terms. That's not a legal conclusion. That's a *lookup*. A query against a rights layer that resolves, in machine time, for a hundred million works.

Courts can rule that the query must be made. They cannot build the thing that answers it. No verdict, however sweeping, produces a registry.

So the honest reading of this moment is that both of 2026's marquee developments — the watermark rollout and the training-data litigation — point at the same missing floor. Detection tells platforms what's synthetic. Litigation tells AI companies what they owe. Neither tells anyone who owns what, in a form that settles.

I wrote a book about this gap — *The Human Authenticity Layer* — and the argument has only compressed since: origin and ownership are the two marks AI can't fake, and neither one lives inside a file. They live in records. The creators who come through this era owning something won't be the ones whose files carried the best labels. They'll be the ones whose claims were registered somewhere that couldn't be transcoded away.

At Suede Labs we build that layer — proof of creation, programmable rights, royalty routing — because detection was never the finish line. It was the warm-up.

The question "is this AI?" is answered.

The question "whose is this?" is still open. That's the one worth building for.
