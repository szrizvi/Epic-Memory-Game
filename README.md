# Pre-work - _Memory Game_

**Epic Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program.

Submitted by: **Zainab Rizvi**

Time spent: **6** hours spent in total

Link to project: https://glitch.com/edit/#!/charming-voltaic-seashore

## Required Functionality

The following **required** functionality is complete:

- [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
- [x] "Start" button toggles between "Start" and "Stop" when clicked.
- [x] Game buttons each light up and play a sound when clicked.
- [x] Computer plays back sequence of clues including sound and visual cue for each button
- [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess.
- [x] User wins the game after guessing a complete pattern
- [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

- [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
- [x] Buttons use a pitch (frequency) other than the ones in the tutorial
- [x] More than 4 functional game buttons
- [x] Playback speeds up on each turn
- [x] Computer picks a different pattern each time the game is played
- [x] Player only loses after 3 mistakes (instead of on the first mistake)
- [ ] Game button appearance change goes beyond color (e.g. add an image)
- [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
- [ ] User has a limited amount of time to enter their guess on each turn

## Video Walkthrough (GIF)

If you recorded multiple GIFs for all the implemented features, you can add them here:

Winning:

![](https://i.imgur.com/Hp4hC9q.gif)

Winning with different secret pattern:

![](https://i.imgur.com/oLelmaq.gif)

Losing after 3 mistakes:

![](https://i.imgur.com/ygyvOdj.gif)

## Reflection Questions

**1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here.**

https://www.w3schools.com/cssref/

**2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words)**

I struggled with getting the right value for `clueHoldTime`. I wrote the `guess()` function and also implemented the bonus feature of speeding up the game at the same time, which may not have been the best idea. Once I tested the game, I saw that it would only play the first few clues if the guesses were correct, with the exception of the first run where it played all eight. To find the problem, I checked the console log where I saw that the game was still playing clues even though they did not show on the web page.

I knew this meant that there was something wrong with the duration of my clues. Even though I had timed it to decrement just enough to fit all eight clues, I would also need a reset for the clueHoldTime variable, which was why it was only working in the first run and not any of the ones that followed. To fix this was simple, I initialized `clueHoldTime` to `1000` where I created the global variable.

However, even after this change, I was still running into the same error. I had the console log to help again, where I found that after a single guess, multiple instances of `???play single clue: [btn]???` were being printed to the log. This meant the `playClueSequence()` was being called more times than necessary. Finally, I found the problem was in my `guess()` function - I had my logic for checking the guess in a loop, since I initially thought it would need to iterate for each clue in the pattern. Taking the logic out of the loop resolved my error and the game ran smoothly from there!

In hindsight, it would have been easier to figure this out had I tested my game separately after implementing each of the functions.

**3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words)**

Since this was my first time doing web development, this submission has made me excited and curious to learn more about the subject. Specifically, something I definitely want to explore is how websites are kept secure, and what kind of attacks a website that is not secure is vulnerable to. For example, how would a website that needs to take in sensitive information from a user, such as a password or bank details, ensure the privacy of a user???s information? Would encryption be a good enough to keep the website secure, or are there other methods implemented as well?

I would also love to learn about the the javascript language, and why it is preferred for web development over other languages. What specific features make it more compatible for websites, and is it only applicable for use on the client-side, or can it also be used for the server-side programming?

**4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words)**

One thing I would love to delve deeper into is how much I can alter the design of my web page through the rules in CSS. Many websites I have visited have cool animations for elements that appear as you scroll down the page, and I would love to implement something similar with the game buttons on my webpage, i.e. only have them fade in once the start button is pressed. In addition, I would like to spend more time to implement the bonus features I did not have a chance to finish, especially having the buttons play different audio than the generated tones. Currently, I have chosen the frequencies for each tone to be that of a musical note (a-f since I have 6 buttons). To better this, I thought to replace the tones of each button with piano notes, and this way the secret sequence can be a melody to a song. This could also be extended to being a way to helping the player learn the song.

## Interview Recording URL Link

[My 5-minute Interview Recording](https://drive.google.com/file/d/1J_28cfSgI0Srn0qFSDbQiQ2SYfC68knv/view?usp=sharing)

## License

    Copyright Zainab Rizvi

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
