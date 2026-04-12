# Arthur Lee Samuel

**Born:** December 5, 1901, Emporia, Kansas
**Died:** July 29, 1990 (aged 88), Stanford, California

## Overview

Arthur Samuel was an American electrical engineer and computer scientist who coined the term "machine learning" in 1959, wrote the first self-learning checkers program (one of the earliest machine learning programs ever demonstrated), and staged the first public television demonstration of artificial intelligence. His 1959 IBM Journal paper remains a foundational document of reinforcement learning.

## Education

| Year | Degree / Institution | Notes |
|------|---------------------|-------|
| 1923 | B.S., College of Emporia (Kansas) | Undergraduate |
| 1926 | M.S. in Electrical Engineering, MIT | Remained as instructor for two years |

## Career

### Bell Laboratories (1928--1946)
Samuel joined Bell Labs in 1928, where he worked primarily on vacuum tube research and, during World War II, on radar development and improvements.

### University of Illinois at Urbana-Champaign (1946--1949)
After the war Samuel became Professor of Electrical Engineering at Illinois. He was an initiating figure in the early **ILLIAC** computer project, the Illinois-built stored-program machine that was one of the IAS-class machines -- but he left the university before the ILLIAC was complete and before he could run any game-playing experiments on it.

### IBM Poughkeepsie (1949--1966)
Watson Jr. and Hurd hired Samuel into IBM's Applied Science Division. He was supervised by **Nathaniel Rochester**, who encouraged his AI experiments. At IBM, Samuel fell in love with the IBM 701 and began the work for which he is remembered.

He retired from IBM in 1966.

### Stanford University (1966--1990)
After IBM, Samuel joined the Stanford University Computer Science Department as a professor. He remained active at Stanford for the rest of his life, dying there on July 29, 1990.

## Key Contributions

### The Checkers Program (1952--1966)

Samuel began coding his checkers-playing program in 1952 on the IBM 701. He chose checkers over chess for practical reasons: simpler rules, smaller branching factor, and a board state that fit comfortably within the 701's 2048 words of main memory. The game had enough strategic depth to serve as a laboratory for learning algorithms.

The program incorporated two forms of learning that had never been implemented before in a computer program:

1. **Rote learning** -- the program memorized every board position it had evaluated together with the minimax value computed from it. Re-encountered positions therefore came with free extended look-ahead built in, at no additional computation.

2. **Generalization learning** -- described fully in the 1959 paper. The program played itself: an "Alpha" side using the current evaluation weights played against a "Beta" side using fixed reference weights. Alpha's weights were updated based on the difference between its predictions and the values obtained from deeper search. Richard Sutton (modern father of reinforcement learning) later identified this mechanism as the first implementation of **temporal-difference learning** -- the same technique that, six decades later, powered AlphaGo and AlphaZero.

### February 24, 1956 -- Television Demonstration
On the morning of February 24, 1956, IBM broadcast a live television demonstration of the checkers program on one of the major morning news programs. Samuel operated the machine from Poughkeepsie; the TV host Will Rogers Jr. was in the studio with a checkers expert who played against the program for about an hour via remote connection. Thomas Watson Sr. -- in the last months of his life, dead by June 1956 -- had arranged for IBM shareholders to watch the broadcast. He predicted the stock would rise 15 points. It rose 15 points overnight. This is widely cited as the first public television demonstration of what is now called artificial intelligence.

### The 1959 Paper and "Machine Learning"
Samuel published **"Some Studies in Machine Learning Using the Game of Checkers"** in the *IBM Journal of Research and Development*, volume 3, pages 210-229, in July 1959. This paper is the first printed source for the term **"machine learning."**

The most famous definition attributed to Samuel -- "the field of study that gives computers the ability to learn without being explicitly programmed" -- does not appear verbatim in the paper. It is a universally cited paraphrase. The actual sentence from the 1959 paper is:

> "Enough work has been done to verify the fact that a computer can be programmed so that it will learn to play a better game of checkers than can be played by the person who wrote the program."

### The 1962 Nealey Match and 1966 Debacle
In 1962, on the much more powerful IBM 7094, Samuel's program played a publicized match against **Robert Nealey**, whom IBM press materials described as a Connecticut checkers champion and master player. The program won. IBM marketing made considerable noise about the result. In reality, Nealey was not a master at the time -- he did not win the Connecticut state championship until 1966 -- and when Samuel's program subsequently played actual world-class players **Walter Hellman** (world champion) and **Derek Oldbury** (English champion) in 1966, it lost all eight games rather easily. That result received no publicity. The 1962 hype followed by the 1966 rout is a template repeated in every AI cycle since.

### Second Paper (1967)
Samuel published a second checkers paper, "Some Studies in Machine Learning Using the Game of Checkers II -- Recent Progress," in the *IBM Journal of Research and Development*, volume 11, pages 601-617, in 1967, reporting further improvements including alpha-beta search enhancements.

## Awards and Honors

- IEEE Computer Society **Computer Pioneer Award** (1987)

## Connections to Others

- **Nathaniel Rochester** -- Rochester supervised Samuel's checkers program at IBM Research; Samuel worked within Rochester's AI research group at IBM Poughkeepsie
- **Claude Shannon** -- Samuel attended Shannon's 1948 talk on computer chess and left, by his own account, mistakenly convinced Shannon had already built a working chess machine; this spurred Samuel's own program
- **Jule Charney / ILLIAC connection** -- Samuel initiated the ILLIAC project at Illinois; the same IAS-class machine architecture was used by Charney's group for NWP research at Princeton
- **Richard Sutton** -- Sutton (co-author of *Reinforcement Learning: An Introduction*) retrospectively identified Samuel's 1959 generalization-learning mechanism as the first implementation of temporal-difference learning
- **John McCarthy / Dartmouth** -- Samuel's checkers program was one of the demonstrations discussed at the 1956 Dartmouth AI summer conference
- **Thomas Watson Sr.** -- Watson Sr. arranged the 1956 TV broadcast and publicly predicted its stock-market effect, one of his last public acts before his death in June 1956

## Key Publications

- Samuel, A.L. (1959). "Some Studies in Machine Learning Using the Game of Checkers." *IBM Journal of Research and Development*, 3(3), 210--229.
- Samuel, A.L. (1967). "Some Studies in Machine Learning Using the Game of Checkers II -- Recent Progress." *IBM Journal of Research and Development*, 11(6), 601--617.

## Sources

- [Arthur Samuel (computer scientist) -- Wikipedia](https://en.wikipedia.org/wiki/Arthur_Samuel_(computer_scientist)) -- Accessed: 2026-04-08
- [Computer Pioneers -- Arthur Lee Samuel (IEEE Computer Society)](https://history.computer.org/pioneers/samuel.html) -- Accessed: 2026-04-08
- [Professor Arthur Samuel -- Stanford Computer Science memoriam](https://legacy.cs.stanford.edu/memoriam/professor-arthur-samuel) -- Accessed: 2026-04-08
- [Arthur Samuel -- IEEE Computer Society profile](https://www.computer.org/profiles/arthur-samuel/) -- Accessed: 2026-04-08
- [Arthur Samuel's Legacy -- University of Alberta Chinook project](https://webdocs.cs.ualberta.ca/~chinook/project/legacy.html) -- Accessed: 2026-04-08
- [Samuel's Checkers Player -- Sutton & Barto RL textbook online](http://www.incompleteideas.net/book/ebook/node109.html) -- Accessed: 2026-04-08
- [Arthur Samuel -- History of Information](https://www.historyofinformation.com/detail.php?id=779) -- Accessed: 2026-04-08
