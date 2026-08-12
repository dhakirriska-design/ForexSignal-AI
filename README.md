# Forex Signal AI v2 — Realtime Signal

Versi 2 menambahkan arsitektur realtime:
- WebSocket Twelve Data untuk quote harga terbaru
- REST time_series sebagai bootstrap candle 1m/5m/15m
- EMA 9/21, RSI 14, MACD 12/26/9, Bollinger Bands 20/2
- Candle confirmation
- BUY / SELL / WAIT
- Confidence = skor kondisi teknikal, BUKAN jaminan probabilitas menang
- Entry price
- Expiry 1M / 5M
- Countdown candle
- Riwayat sinyal
- Statistik hasil berdasarkan candle berikutnya
- Reconnect WebSocket dan heartbeat
- Notifikasi lokal saat sinyal kuat

Twelve Data:
REST: https://api.twelvedata.com
WebSocket: wss://ws.twelvedata.com/v1/quotes/price

Twelve Data memerlukan API key. WebSocket realtime saat ini tersedia mulai paket Pro menurut dokumentasi Twelve Data.
Quote provider dapat berbeda dari quote yang tampil di Olymp Trade.

Build:
Android Studio -> Open project -> Sync -> Build APK.
