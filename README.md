catan
-----

Package catan provides models for representing and manipulating a game of catan

Board coordinates must be specified as described in module [`hexgrid`](https://github.com/rosshamish/hexgrid).

Class Game supports undo and redo.

Supports Python 3. Might work in Python 2.

> Author: Ross Anderson ([rosshamish](https://github.com/rosshamish))

### Installation

```
pip install catan
```

### Usage

```
import catan.board
import catan.game
import catan.trading

players = [Player(1, 'ross', 'red'),
           Player(2, 'josh', 'blue'),
           Player(3, 'yuri', 'green'),
           Player(4, 'zach', 'orange')]
board = catan.board.Board()
game = catan.game.Game(board=board)

game.start(players=players)
print(game.get_cur_player())  # -> ross (red)
game.buy_settlement(0x37)
game.buy_road(0x37)
game.end_turn()
...
game.roll(6)
game.trade(trade=catan.trading.CatanTrade(...))
game.undo()
game.redo()
game.play_knight(...)
game.end_turn()
...
game.end()
```

See [`catan-spectator`](https://github.com/rosshamish/catan-spectator) for extensive usage.

### Documentation

Most classes and modules are documented. Read the docstrings! If something is confusing or missing, open an issue.

### License

GPLv3