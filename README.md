# Claude Games

Single-file HTML games you play against Claude Sonnet inside Claude Desktop's artifact pane.

Each game is a self-contained `.html` file. Drop it into a conversation with Claude and ask Claude to render it as an artifact — the artifact makes the API calls for Claude's moves using your session. No API key, no backend.

## Games

| Game | File | Description |
|---|---|---|
| Connect Four | [`connect-four.html`](connect-four.html) | Classic 7×6 drop-four vs Claude. Coin toss decides who goes first. |
| Chess | [`chess.html`](chess.html) | Full FIDE rules (castling, en passant, promotion, 75-move draw). Board state sent as markdown; legal moves pre-computed client-side. |

## How to play

1. Open a conversation in [Claude Desktop](https://claude.ai/download) or claude.ai.
2. Paste the raw contents of a game file into the chat (or link to the raw GitHub URL).
3. Ask Claude to render it as an HTML artifact.
4. Play in the artifact pane.

Raw URLs:
- `https://raw.githubusercontent.com/trevorbyrum/claude_games/main/connect-four.html`
- `https://raw.githubusercontent.com/trevorbyrum/claude_games/main/chess.html`

## How the AI works

Each game serializes the board to a markdown table, pre-computes all legal moves (so Claude never picks an illegal one), and asks Claude to reply with a single move. A deterministic fallback engine kicks in if Claude's response fails to parse or the suggested move is illegal.

## License

[MIT](LICENSE)
