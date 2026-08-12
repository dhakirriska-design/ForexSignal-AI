# v2 implementation notes

## Signal engine
Use the latest CLOSED candle for the actual signal to avoid repeated intrabar signals.
Rules:
BUY score:
+2 EMA9 > EMA21
+1 RSI 50-70
+1 MACD > signal
+1 close > BB middle
+1 bullish candle confirmation
SELL is mirrored.
WAIT when absolute score < 4.

Confidence is normalized from the score and should be displayed as "signal strength", not win probability.

## Realtime
1. REST fetch 120 historical candles.
2. Build indicators.
3. Open WebSocket.
4. Subscribe to EUR/USD (or selected symbol).
5. Update live price.
6. At each minute boundary, finalize candle and recalculate.
7. Keep previous signal until the next closed candle.
8. Reconnect after network failure.

## Expiry
1M: evaluate the next closed 1-minute candle.
5M: evaluate the next closed 5-minute candle.

## Important
Do not automatically place orders on Olymp Trade.
