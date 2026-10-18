# Farsi Quest

Learn Persian (Farsi) in the Duolingo style: a learning path with units and short lessons, hearts, a daily goal, a streak, a weekly league, gems and a practice hub full of games. The interface is in Dutch.

It is a single static web page with no backend. Open `index.html` or use GitHub Pages. Progress is stored in your browser (localStorage).

## Content
- `data.js` and `data2.js` hold about 2,600 words and phrases in 32 categories. Each entry has Persian script, a transliteration, a Dutch meaning and a level from 1 to 3.
- `zinnen.js` holds 575 sentences. Each has Persian, a word-by-word aligned transliteration, a Dutch translation and a level.
- The vocabulary was generated with Claude and checked automatically: no duplicates, Persian ی/ک instead of Arabic forms, and correct token alignment. It has not been checked by a native speaker.

## How the app is built (what was copied from Duolingo and others)
| Mechanism | Source of inspiration | In Farsi Quest |
|---|---|---|
| Learning path with units and lessons | Duolingo path | 32 units of up to 6 lessons, unlocked in order, each followed by a unit review |
| Lesson of about 15 exercises with mixed types | Duolingo | Introducing new words, multiple choice in both directions, typing, tapping pairs, building sentences from a word bank (both directions), choosing the missing word, and listening (when the device has a Persian voice) |
| Repeating mistakes at the end of a lesson | Duolingo | Every wrong answer comes back at the end of the lesson |
| Hearts | Duolingo | 5 hearts, minus 1 per mistake in a lesson, plus 1 every 30 minutes, and refilled through practice or with gems |
| Memory model per word | Duolingo half-life regression and Anki FSRS | Each word has a stability in days. Recall probability follows the FSRS curve, and a word comes back once that probability drops below 90%. Mistakes lower the stability sharply |
| Recognise first, then produce | Research on receptive versus productive vocabulary | New words start as multiple choice. Better-known words have to be typed |
| Personalised practice and a mistakes list | Duolingo Practice Hub | Practice your weakest words or your recent mistakes, each worth +1 heart |
| Legendary level | Duolingo Legendary | A test of 16 questions with at most 2 mistakes and a time limit, rewarded with a crown |
| Streak, streak freeze, daily goal, XP | Duolingo | Included, with the freeze bought using gems |
| Weekly league with promotion and relegation | Duolingo leagues | 10 players with simulated opponents. The top 3 are promoted and the bottom 2 relegated, across 6 tiers |
| Short daily sessions | Research on spaced repetition | Daily goal of 10 to 100 XP |

Arcade games in the practice hub: word quiz, typing, building sentences, fill in the gap, listening, match-race, survival and the alphabet, plus a dictionary that shows the recall probability of each word.

## Sources
- Duolingo exercise types: https://duolingo.fandom.com/wiki/Exercise
- Duolingo, "How we learn how you learn" (half-life regression): https://blog.duolingo.com/how-we-learn-how-you-learn
- Settles & Meeder 2016, *A Trainable Spaced Repetition Model for Language Learning*: https://preview.aclanthology.org/fix_video/P16-1174.pdf
- Implementing FSRS in 100 lines: https://borretti.me/article/implementing-fsrs-in-100-lines
- Anki on FSRS vs SM-2: https://docs.ankiweb.net/faqs/what-spaced-repetition-algorithm
- Duolingo practice hub: https://blog.duolingo.com/ways-to-practice-in-duolingo
- Spaced repetition for vocabulary retention (systematic review): https://riset.unisma.ac.id/index.php/JREALL/article/view/25562
