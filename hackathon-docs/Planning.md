Feel free to edit. This is an overview of ongoing tasks, a briefing, an entry point.

Code Repository: [https://github.com/kudosscience/aixbio-apart-hackathon](https://github.com/kudosscience/aixbio-apart-hackathon)

# What do we want to achieve:

1. Make a dataset of potentially dangerous sequences using ProteinMPNN: same 3D structure as dangerous proteins, different aminoacid chain and different DNA  
2. Trick SecureDNA into flagging them as safe  
3. Make a tool based on embedding (ESM2) similarity screening that will recognize them as dangerous  
4. Yay, we’ve done better than SecureDNA, write a preprint

# Tasks:

1. ### Make a dataset of potentially dangerous sequences using ProteinMPNN: same 3D structure as dangerous proteins, different aminoacid chain and different DNA.

[Henry (phytographer)’s notebook](https://colab.research.google.com/drive/1aqI8UqAVkDSGEKLJ8wBaDNHAavVbQHtD?usp=sharing) has this covered; we send ProteinMPNN 3D structure of a protein, and it offers 8 other aminoacid sequences that could generate the same 3D structure, but are different.  
**TODO:**

* **select which 3D structures to modify. We can only cover about 500, because ProteinMPNN eats a lot of compute.**

Possible approaches:

- run a set of 15 random modified dangerous proteins, 8 variants each, through SecureDNA. See if it fails to spot danger. Repeat. Search for a pattern. Once the pattern is found, select 500 proteins based on this pattern.  
- ?

Probably not:

- top 500 most popular toxins/virulence factors. SecureDNA are probably not idiots, and they’ve probably already protected themselves against every possible modification of popular dangers.


2. ### Trick SecureDNA into flagging them as safe

We currently have a placeholder instead of SecureDNA API call. Someone has to write the actual thing.  
**TODO:**

* **Write a function that accepts amino acid sequence as an input, transforms it into DNA sequence, sends to SecureDNA screening and outputs the result.**  
* **Time this function. Maybe screening will become a bottleneck.**


3. ### Make a tool based on embedding (ESM2) similarity screening that will recognize them as dangerous

[Polina (Sklyano4ka)’s notebook](https://colab.research.google.com/drive/1L6Z0xKIL1n6Ta1mP5EQBoBHqPd__ub3C?usp=sharing) is trying to cover this.  
[Raw embeddings (not centralized) can be found here](https://drive.google.com/drive/folders/1Mc_Rj1NSqcPow2TZVWRHPtbjz_DnBodM) (7000+ toxins and virulence factors, 25000 negative control proteins, recalculating them will take 4 hours. Don’t. Just load these files to Colab.)  
**TODO:**

* **integrate support for reverse DNA thread scanning and multiple ORFs. Currently the code selects the longest ORF.**  
* **check if the notebook actually works. It already has a code for batch screening and a wget for NIST testing dataset (TP in metadata \- a dangerous sequence, True Positive; TN \- a neutral sequence, True Negative). Someone just has to launch this. But turn off the SecureDNA placeholder. Just test the embedding cosine similarity screening.**  
* **integrate SecureDNA API call (also in Step 2).**  
* **Maru wanted to try to integrate attention pooling instead of mean pooling. Can, in theory, largely improve performance.**


4. ### Yay, we’ve done better than SecureDNA, write a preprint

TODO:

* get there.  
* if we got there: shove our final code and results into Claude, also shove there examples of winning preprints from previous hackathons (can be found in Discord). Ask it to write us a preprint.

Deadline: 23:59 GMT Sunday 26th

# Team Accesibility Schedule

Polina (Sklyano4ka): offline 25.04 all day. Active 26.04 all day, from 7:00 GMT and indefinitely.  
Henry (phytographer): Active Sat 25.04 and Sun 26.04 all day \- intermittent breaks for meetings  
Elina: ?  
Marie (Maru): ?  
Alessandro: ????????  
