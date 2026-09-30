# My Projects
With the exception of Solofolio, all projects listed here were developed entirely by me.

## [Solofolio](http://solofolio.net/) - Internship (2026-present)
I contributed to the development of Solofolio, a web app built using Ruby on Rails that allows users to upload images to create portfolio websites. During my time at Solofolio, I did the following:
- I improved the image management UI, allowing users to more easily delete many images at once. I implemented this feature across the stack, from the frontend JavaScript to the backend Rails endpoints.
- I helped optimize page load times by configuring the server to use [Cloudfront](https://aws.amazon.com/cloudfront/), a content delivery network. I implemented this safely using feature flagging to ensure no users were adversely affected.
- I made the project follow software engineering best practices by setting up a CI pipeline for automated testing and linting via [GitHub Actions](https://github.com/features/actions).

## [Arachnomechanica](https://github.com/rclaytondev/arachnomechanica) (2025-present)
*Arachnomechanica* ([play it online!](https://rclaytondev.github.io/arachnomechanica/)) is a procedurally-generated platformer game about creatures with complex emergent behavior, designed with a focus on allowing a large degree of player skill. The following are some of the core technical challenges I solved in the project:

**Always-solvable level generation**: A central feature of the game is gates that all toggle every time the player goes through one. It would be easy to accidentally create an impossible or trivial level with these, so I created a sophisticated algorithm that intelligently places rooms to avoid these issues. To create the general shape of the level, the algorithm first creates a "main path" through the level, then randomly adds branches off the path (based off the technique used in one of my favorite games, *Spelunky*). To fill in this shape with actual rooms, the algorithm initially makes each room maximally connected, then replaces each room with a less-connected version, reverting to the previous state if doing so makes the level impossible to traverse.

**Dynamic entity unloading**: A core technical component of the game is the data structure used to store game entities. Since there are no limits to the player's exploration, I needed a special solution to ensure that the game's performance did not degrade as the game generates more content. To do this, I combined maps and sets to create a custom data structure that allows for constant-time rectangular collision queries. I used inheritance to decouple this custom data structure from the game-specific logic.

**Custom physics engine**: *Arachnomechanica* also features a more flexible and robust physics engine than my previous games, inspired by the approach used for another of my favorite games, *Celeste*. The physics engine supports non-rectangular hitboxes, slopes, and objects pushing other objects, and elegantly avoids potential bugs by ensuring that the system never reaches an invalid state, as opposed to by correcting invalid states once they occur.

## [Project Euler](https://github.com/rclaytondev/programming-challenges) (2020-present)
[Project Euler](https://projecteuler.net) is a collection of challenging problems that require mathematical insights and efficient algorithms to solve. I have solved over 150 Project Euler problems, placing me in the top 0.4% of users. To solve these problems, I have written algorithms in JavaScript, TypeScript, C++, and Haskell. I am particularly proud of my solution to the following problems:
- [Problem 544: Chromatic Conundrum](https://projecteuler.net/problem=544) (2026): I realized that the [deletion-contraction recurrence](https://en.wikipedia.org/wiki/Deletion%E2%80%93contraction_formula) would not be nearly efficient enough to compute the [chromatic polynomial](https://en.wikipedia.org/wiki/Chromatic_polynomial) of the graph in the problem, so I used a custom approach that takes advantage of symmetries of the graph. I then independently re-derived and implemented [Faulhaber's formula](https://en.wikipedia.org/wiki/Faulhaber%27s_formula) and used it to finish the problem.
- [Problem 502: Counting Castles](https://projecteuler.net/problem=502) (2025): To handle the three different inputs in the problem, I realized three different algorithms would be required. I created three memoized recursive divide-and-conquer algorithms with time complexities of $O(w \cdot h)$, $O(h^3 \log w)$, and $O(w^2 \log h)$.
- [Problem 227: The Chase](https://projecteuler.net/problem=227) (2024): I wrote an algorithm that converted the problem into a large system of equations, which it then solved using [Gaussian elimination](https://en.wikipedia.org/wiki/Gaussian_elimination). To avoid the accumulation of numerical inacurracies, I used a custom infinite-precision rational number class instead of using ordinary floating-point numbers.

## [Mathematical Text Editor](https://github.com/rclaytondev/math-editor) (2023-2024)
After becoming dissatisfied with the options available for editing documents containing mathematical notation, I created my own text editor with the goal of allowing the user to write math digitally as fast as when writing by hand. The editor supports all the basic features needed to write advanced math, including arbitrary nested fractions, superscripts and subscripts, parentheses that dynamically expand to fit their content, and Greek letters via an autocomplete system. Other features include keyboard shortcuts and multi-cursor editing.

The editor is a desktop app written in TypeScript using [Electron](https://www.electronjs.org/), using the libraries [Chai](http://chaijs.com/), [Mocha](https://mochajs.org/), and [Playwright](https://playwright.dev/). It supports reading and writing from files using a custom JSON format I created for storing mathematical notation.

## [Physics Simulation](https://github.com/rclaytondev/physics-simulation) (2021-2022)
I created an advanced physics engine that uses conservation of angular momentum to accurately simulate collisions between circular and polygonal objects.

## [Stick Dungeon](https://github.com/rclaytondev/stick-dungeon) (2018-2020)
*Stick Dungeon* ([play it online!](https://rclaytondev.github.io/stick-dungeon/)) is a game in which the player explores an infinite, procedurally-generated dungeon while fighting enemies, collecting treasure, upgrading their character, and completing platforming challenges. The game contains 3 playable character classes, 17 types of collectable items, 7 types of enemies, 20 types of rooms, and 18 types of structures that can generate in rooms. The game is written in JavaScript.

## [Hypocube Translocation](https://github.com/rclaytondev/hypocube-translocation#hypocube-translocation) (2019)
*Hypocube Translocation* is an abstract puzzle game in which the player must push a block onto its goal, using extenders that can push or pull an object in a certain direction. The game features a total of 25 handcrafted puzzles. To help with the creation of these puzzles, I created a level editor as well as a brute-force solver to detect unintended solutions.

Unlike my other games, *Hypocube Translocation* is written in Java and can be played as a desktop app.

## [Random Survival Game](https://github.com/rclaytondev/random-survival-game) (2016-2019)
*Random Survival Game* ([play it online!](https://rclaytondev.github.io/random-survival-game/)) is a 2D platformer game in which the player must survive a series of 16 different dangerous events, such as lasers, missiles, and deadly robots. The player can collect coins to purchase any of 6 items in a shop, such as a coin magnet, a jump boost, or a second life. Most of the items are upgradable and have 3 different variants. There are also 9 achievements that can be earned by fulfilling various goals.
