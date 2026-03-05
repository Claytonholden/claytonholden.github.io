# NCL — CAN Bus Analysis (Ohm Motors)

## Goal
Answer questions like:
- How many unique CAN IDs exist?
- How many speed messages exist?
- What is the maximum speed (mph)?

## What I was given
A code snippet that defines how speed is encoded:

- `speed_id = 589`
- `speed_pos = 3`
- Speed is 2 bytes (big-endian) starting at byte index 3
- Convert from centi-kph → kph → mph

## Approach (repeatable)
### 1) Filter to just the speed frames (ID 589)
Tool options:
- Wireshark display filter
- tshark field extraction
- Export CSV and filter there

**Key idea:** Only frames with CAN ID **589** contain speed updates.

### 2) Extract raw payload bytes
Once you have the speed frames, you need the data bytes in order.

If you export to CSV, make sure you are reading the raw payload as hex bytes.

### 3) Apply the code snippet math exactly
The important parts:
- Read the two bytes at positions `3` and `4`
- Combine big-endian: `raw = (data[3] << 8) + data[4]`
- Convert: `kph = raw / 100`
- Convert: `mph = kph * 0.6213751`

### 4) Find the max mph
Compute mph for every frame, track the maximum, and round to nearest hundredth.

## Common mistakes I hit
- Picking the wrong two bytes (end of payload instead of positions 3–4)
- Treating the value as little-endian instead of big-endian
- Not dividing by 100 (centi-kph)
- Using the wrong conversion factor

## Validation check
When the math is correct, the top speed matched the NCL expected output.

## Tools used
- Wireshark / tshark for filtering
- Python for calculating and taking the max
