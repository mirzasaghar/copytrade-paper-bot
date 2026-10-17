# Copy-trade bot (paper mode)

## What it is
A single page that watches Solana wallets, spots their buys and sells on new coins, and copies
them with a paper balance. Nothing is connected to a real wallet and it never asks for a key.

## How to run it
1. Open https://mirzasaghar.github.io/copytrade-paper-bot/ in Chrome, or double click
   copytrade-paper-bot.html from this folder. It works the same either way.
2. Press "Find profitable wallets". It takes under a minute. It collects the traders on
   today's trending coins, checks each one's last 40 transactions, and adds only the ones that
   are in profit and meet your rules (by default 3 or more closed coins, 50% or more of them won,
   and a median hold of 2 minutes or longer, so fast flippers that can't be copied are left out). The table shows
   every wallet it checked and the exact reason it was kept or skipped. You can also paste your own wallets,
   one per line.
3. Set the rules (size per copy, minimum liquidity and 24h volume, maximum coin age, take
   profit and stop loss) and press Start.
4. It first replays each wallet's recent trades so you see results straight away, then checks
   every wallet twice a second and copies new trades live. "Behind leader" at the top shows how
   long after the wallet's own trade the copy happened, counted in 400 ms Solana slots. In a test
   on 17 Oct 2026 the median was 0.4 s on the free RPC. Keep the tab open; it still runs in the
   background, but closing it stops the bot.
5. "Export closed trades" downloads every closed trade as a CSV file.

## Notes
- Fills use the leader's own trade price plus your slippage and fee settings.
- The free public RPC (publicnode) is fine for testing. For live trading use a paid RPC such as
  Helius or QuickNode and paste its URL in the Solana RPC box.
- Settings, paper trades and the light or dark choice are saved in your browser, so they're
  still there next time.
- Coin data comes from DexScreener, prices from Jupiter.




