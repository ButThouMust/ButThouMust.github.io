I wanted to make a basic site for the ROM hacking projects I've done, am doing,
or am interested in doing.

# <ins>A little about me</ins>
I have a bachelor's degree in computer engineering.

I'm a Japanese self-studier and have a JLPT N3 certificate from December 2025.
I'm tempted to say I "only" have N3 since there's still much more for me to
learn with the language.

* * *

# <ins>Released translation patches</ins>
## Otogirisou (Super Famicom)
- [Patch download](https://github.com/ButThouMust/otogirisou-english/releases/latest)
- [Source code](https://github.com/ButThouMust/otogirisou-tools)

## Kamaitachi no Yoru (Super Famicom)
- [Patch download](https://github.com/ButThouMust/kamaitachi-sfc-english/releases/latest)
- [Source code](https://github.com/ButThouMust/kamaitachi-sfc-english)

* * *

# <ins>Games I'd be interested in hacking</ins>
- Mr. Driller G (PS1)
- Getsumen no Anubis (SFC) - somewhat interested

* * *

# <ins>Games I've dug around in</ins>
These are somewhat sorted by priority, from highest to lowest.

## Machi: Unmei no Kousaten (PS1)
Yes, really. I made font and script dumpers for this, and filled in the table
files as I was reading through the stories. IDing every character in all the
text encodings was a huge pain in the butt. Each possible combination of
protagonist and day uses its own unique encoding!

Having finished the game with all the endings, I completely understand both why
Machi is so highly regarded in Japan, and why no fan translation has appeared
yet for it. One protagonist's story has several *virtually untranslatable*
text passages, that depend on reading Japanese text in specific ways.

## Otogirisou Sosei-hen (PS1)
Font identified. Proprietary graphics decompressor (flavor of LZSS) created.
Script dumper program hopefully finished. I have a script dump but have not
tried to create a text reinserter.

I don't have any major experience with PS1 hacking but have published a
[Github repo](https://github.com/ButThouMust/otogirisou-ps1) with a handful of
my findings with looking at the game's code in Ghidra. Please contact me if you
would like to contribute to it or use it as a base for a project!

## YaruDora series (PS1)
I don't know how serious of a project this will become, but this probably
deserves its own page/repo someday.

### About the games
A basic synopsis if you're not familiar: YaruDora (やるドラ, roughly "a drama
that you do," as opposed to simply watch) is a series of visual novels from a
developer you probably wouldn't guess was a second-party Sony dev by name alone:
Sugar & Rockets. They are fully animated and, apart from the protagonist, fully
voiced, with animation from Production IG. The four PS1 games each take place in
a different season and feature women with amnesia. There are two other games on
PS2: Scandal, and a two-part game based on Blood The Last Vampire. All the games
minus Scandal would get rereleased on PSP.

I have PS1 copies of Double Cast (100.00%) and Kisetsu o Dakishimete (reached a
few endings). I'd like to get Sampaguita and Yukiwari no Hana on PS1, plus
Scandal, someday.

Note: [Double Cast](https://www.romhacking.net/translations/5777/) and
[Sampaguita](https://github.com/Eight-Mansions/yarudora_3_psp) on PSP have
English fan translation patches. I learned of this after finishing Double Cast
PS1. I think, had I known about the patches before buying my copies, I still
would have gotten the much more affordable PS1 releases (~$15 each vs ~$100
each).

### Hacking progress
I've mainly dug around in Double Cast because I don't want to spoil myself with
Kisetsu from digging around in it.

I determined the text encoding and found which files contain the scenario text.
This was enough information for me to make a basic text dumper, for just the
text without the pointers. More on the pointers later.

I confirmed a suspicion I had that the dumper would also work for a few of the
script files in Kisetsu. My reasoning was that Sony published all four PS1 games
during 1998, so Sugar & Rockets probably would have reused file formats and code
between the four games. But I can't say for sure about Sampaguita and Yukiwari
no Hana until I buy copies of them, rip them, and examine their files.

I was able to intuit the text pointers' format (16-bit intra-file offsets).
They exist within part of the text files that I think of as "scripting data,"
separate from the text. Ideally, I would replicate the game's "parse scripting
data" code in the dumper, to give more fine control over how the game syncs up
text, graphics, FMVs, etc. However, Ghidra revealed that the format is much more
complicated than I thought it would be. Hope is not lost, though, because I have
an idea, if less robust, to use the text to find the pointers, as opposed to
using the pointers to find the text like I was hoping for.

## Kamaitachi no Yoru Tokubetsu-hen (PS1)
Some of the script files are compressed. Ghidra's decompilation of the relevant
decompression ASM was really long and complicated, and so I decided to put that
off for another day.

## Mr. Driller A (GBA)
This has my favorite version of the series's Dristone mode. I've identified a
decent amount of the text but haven't gotten around to making text dumpers.

## Valkyrie no Bouken in Namco Anthology 2 (PS1)
I figured out where the text is but don't yet know where the pointers are.

## Magic Knight Rayearth 2nd: The Missing Colors (GB)
I had played this in Japanese and like this the best of the Rayearth games
besides the one on Saturn. It's still a bit simplistic for a JRPG, though. I was
disappointed to find that the script in the existing translation patch had to be
greatly compromised to fit, because the patch creator couldn't repoint the text.

I dug around in this and found a decent amount of text in it, but I wouldn't be
too upset if another group had more signifcant progress in it than me.
