# pi2adl

**pi2adl** is a lightweight Python tool that converts domain lists (such as Pi-hole blocklists) into **AdGuard Home–compatible ADL (AdGuard Domain List) format** by prefixing each domain with `0.0.0.0`.

This makes it easy to reuse Pi-hole blocklists in AdGuard Home or any DNS sinkhole that supports host-style blocking.

---

## Features

- Converts Pi-hole style domain lists
- Skips empty lines and comments
- Avoids duplicating already formatted entries
- Fast and lightweight
- No external dependencies

---

## Example

### Input (`blocklist.txt`)
```
# Ads
googleads.g.doubleclick.net
ads.facebook.com

# Tracking
tracking.example.org
```

### Output (`blocklist.txt.adl.txt`)
```
0.0.0.0 googleads.g.doubleclick.net
0.0.0.0 ads.facebook.com
0.0.0.0 tracking.example.org
```

---

## Requirements

- Python 3.7 or newer

---

## Installation

Clone the repository:

```
git clone https://github.com/natanielbaiao/pi2adl.git
cd pi2adl
```

---

## Usage

Run the script with a domain list file:

```
python pi2adl.py your_list.txt
```

The converted file will be created as:

```
your_list.txt.adl.txt
```

---

## Supported Input

The script automatically ignores:
- Blank lines
- Lines starting with `#`
- Lines starting with `!`
- Entries already starting with `0.0.0.0`

This allows direct use of Pi-hole blocklists.

---

## Use Case

Perfect for:
- AdGuard Home users
- Pi-hole blocklist migration
- DNS filtering setups

---

## License

MIT License

---

## Author

Original project by **Nataniel Baião**  
README maintained by **José**
