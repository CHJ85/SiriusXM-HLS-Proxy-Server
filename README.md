# SiriusXM HLS Proxy Server
A lightweight CLI tool and local HTTP proxy for streaming live SiriusXM radio stations and event streams (`.m3u8` / `.aac`), with channel listing support. Includes the Extra / app-only content.

# Requirements
pip install requests

# Usage
- List available channel IDs  
python sxm.py "user@example.com" "password" -l
- Start the proxy server  
python sxm.py "user@example.com" "password" -p 9999
- Stream a channel  
Pass the channel's channelId or name with a .m3u8 extension to your media player.  
(example mpv http://localhost:9999/45.m3u8 or http://localhost:9999/shade45.m3u8)

# How it works
- Fetches native Akamai HLS (.m3u8) stream URLs directly from SiriusXM's Web Player API.
- Passes through raw AAC audio segments without transcoding or re-encoding.
- Automatically refreshes authentication tokens (SXMAKTOKEN) when sessions expire.

# Disclaimer
This project is intended strictly for personal use and educational purposes.
