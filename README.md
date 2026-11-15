# Distributed Game of Life

A Go coursework implementation of Conway's Game of Life using an RPC client and server. The controller reads an initial PGM image and sends work to a server; the server calculates board states and reports live-cell counts.

## Code and materials

- [`gol/`](gol/) contains the controller, events and image I/O.
- [`server/`](server/) contains the RPC server and board update logic.
- [`stubs/`](stubs/) defines RPC messages; [`sdl/`](sdl/) contains the visualisation.
- [`images/`](images/) and [`check/`](check/) contain example inputs and test fixtures.
- [Original coursework guidance](COURSEWORK.md) describes the provided skeleton and assignment.

## Running

The project uses Go and SDL2. The original guidance includes [SDL setup notes for Windows](content/windows_sdl_native.md). Start the server in one terminal:

```sh
go run ./server
```

Then, from the repository root in another terminal, start the controller:

```sh
go run . -w 16 -h 16 -turns 100 -t 1
```

The client is configured to connect to `127.0.0.1:8030`; the server listens on port 8030 by default. Use `-noVis` to disable the SDL window. The source is a coursework snapshot: the presence of tests and assignment guidance does not imply every requirement is implemented or passing.
