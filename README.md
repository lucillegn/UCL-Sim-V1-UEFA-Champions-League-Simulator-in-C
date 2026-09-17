# UCL Sim V1

An interactive UEFA Champions League simulator written in C.

UCL Sim V1 allows the player to choose a team and go through a simulated Champions League campaign, from the league phase to the knockout stages and final.

The project was built as a practical C programming project to work with structures, arrays, functions, random number generation, probability, and tournament logic.

## Features

* 36 teams divided into 4 pots
* Interactive team selection
* Randomized opponent selection
* Country-based opponent restrictions
* 8-match league phase
* Home and away fixtures
* Team strength ratings
* Random strength variation during matches
* Poisson-based goal simulation
* 3-point win / 1-point draw scoring system
* Playoff qualification based on league-phase points
* Round of 16
* Quarter-finals
* Semi-finals
* Final
* Two-leg knockout ties
* Aggregate score calculation
* Penalty shootouts
* Interactive penalty decisions
* Randomized match and tournament outcomes

## Match Simulation

The match system uses team strength to determine the expected number of goals.

A team's rating is given a random variation before each match, and this value is converted into a goal expectation.

Goals are then generated using a Poisson-based calculation implemented in the `golhesapla()` function.

This allows stronger teams to have a higher expected scoring rate while still allowing unpredictable results.

## Tournament Flow

```text
Team Selection
      |
      v
League Phase
   8 Matches
      |
      v
League Phase Points
      |
      +------------------+
      |                  |
    < 8               8-14
      |                  |
   Eliminated         Playoff
                         |
                         v
                      Round of 16
                         |
                         v
                   Quarter-final
                         |
                         v
                    Semi-final
                         |
                         v
                       Final
                         |
                         v
                    Champion
```

Teams that qualify directly skip the playoff stage and enter the Round of 16.

## Penalty Shootouts

If a two-leg knockout tie finishes level on aggregate, the simulator starts a penalty shootout.

The player controls their own penalty direction and chooses where the goalkeeper should dive against the opponent.

The shootout begins with five penalties per side and continues with additional penalties if the score remains level.

## C Concepts Used

This project focuses on several C programming concepts:

* `struct`
* Arrays
* 2D arrays
* Functions
* Function parameters
* Pointers
* Strings
* `strcmp()`
* `sizeof`
* Random number generation
* `rand()` and `srand()`
* Loops
* Conditional statements
* Mathematical functions
* `math.h`
* Probability and random simulation
* Basic tournament data management

## Teams

The simulator currently contains 36 teams distributed across four pots.

Each team has:

* Name
* Strength rating
* Country code

Example:

```c
typedef struct
{
    char isim[50];
    int guc;
    char ulke[5];
} takim;
```

## Project Status

**Version:** V1

This is the first major version of the project. The main goal of V1 is to build the core Champions League simulation system in C.

Future versions may expand the simulation with more detailed team, player, transfer, and match systems.

## Build

Compile with GCC:

```bash
gcc ucl_sim_v1.c -o ucl_sim_v1 -lm
```

Then run:

```bash
./ucl_sim_v1
```

On Windows:

```powershell
.\ucl_sim_v1.exe
```

## Purpose

This project was created as a hands-on C programming project.

The goal was not only to simulate football matches, but also to practice building a larger program from scratch using C's core programming concepts.

## Version History

### V1

* Team and pot system
* Interactive team selection
* Randomized league-phase fixtures
* 8-match league phase
* Team strength system
* Poisson-based goal simulation
* Playoff and knockout stages
* Two-leg ties
* Aggregate scoring
* Penalty shootouts
