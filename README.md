# SiriusXM HLS Proxy Server
A Python HTTP proxy that authenticates with your SiriusXM account and serves radio station streams as standard .m3u8 playlists. Useful for playing live channels in media players like mpv or VLC without keeping a browser open.

# Requirements
pip install requests

# Usage
- List available channel IDs  
python sxm.py "user@example.com" "password" -l
- Start the proxy server  
python sxm.py "user@example.com" "password" -p 9999
- Stream a channel  
Pass the channel's channelId or name with a .m3u8 extension to your media player.  
(example mpv http://localhost:9999/classicrewind.m3u8)

# How it works
- Fetches native Akamai HLS (.m3u8) stream URLs directly from SiriusXM's Web Player API.
- Passes through raw AAC audio segments without transcoding or re-encoding.
- Automatically refreshes authentication tokens (SXMAKTOKEN) when sessions expire.

# Disclaimer
This project is intended strictly for personal use and educational purposes.
