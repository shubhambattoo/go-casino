# Casino Slot Machine

A small command-line casino slot machine written in Go. The game starts each session with a `$200` balance and lets the player place bets, spin a 3×3 slot grid, and collect winnings for matching rows.

## Features

- Interactive player name and betting prompts
- 3×3 slot-machine spins
- Four symbols with weighted probabilities
- Row-based win detection
- Symbol-specific payout multipliers
- Play until the balance reaches zero or the player enters `0` to quit

## Requirements

- Go 1.26.6 or newer

## Run the game

From the project directory, run:

```bash
go run .
```

Alternatively, build an executable and run it:

```bash
go build -o casino .
./casino
```

## How payouts work

A bet is deducted before every spin. Each row pays when all three symbols match. The payout is calculated as:

```text
winning multiplier × bet
```

The current symbols and payouts are:

| Symbol | Relative frequency | Payout multiplier |
|:------:|:------------------:|:-----------------:|
| A      | 4                  | 20×               |
| B      | 7                  | 10×               |
| C      | 12                 | 5×                |
| D      | 20                 | 2×                |

The frequency values weight how often each symbol appears in the reel. A spin selects distinct positions from the reel for each column.

## Project structure

- `main.go` — game loop, balance handling, and win checking
- `spin.go` — player input, betting, and welcome messages
- `util.go` — reel generation, random spins, and output formatting
- `go.mod` — Go module definition

## Development

Format the source code with:

```bash
gofmt -w *.go
```

Run the available tests with:

```bash
go test ./...
```

## Disclaimer

This is an educational command-line project and does not involve real-money gambling.
