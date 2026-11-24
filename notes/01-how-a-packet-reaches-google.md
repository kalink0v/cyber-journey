# 01 – What happens when I type google.com

**Date:** 2026-11-24
**Source:** TryHackMe Pre Security – Network Fundamentals

## Summary
After typing google.com and pressing Enter, the browser translated the domain name into an IP Address, opens a secure connection to Google's servers, fetches the webpage files, and draws the page on the screen in milliseconds.

## Step by step
0. Input & Browser: The OS and browser process each keystoke and checks against history to show autocomplete options
1. DNS lookup: the browser asks a DNS server for google.com's IP address
2. TCP handshake: SYN → SYN/ACK → ACK
3. HTTPS/TLS: encrypted connection is set up
4. HTTP request: GET / is sent, the server replies with the page

## Security angle
In step 0 an attacker can alter what you type, beware of keylogger, malicious browser extensions.
In step 1 an attacker can trick the device into resolving google.com to a malicious IP address.
In step 2 an attacker can intercept drop or redirect packets across lcoal Wi-Fi or the internet.
In step 3 an attacker can sit in the middle to decrypt traffic or force an unencrypted connection.
In step 4 an attacker can inject malicious code or steal session cookies once the page loads.
