# NCL — Log Analysis Playbook

## Common question types
- Total login attempts
- Unique usernames
- Username with most attempts + count
- Date with most attempts
- Username with logins from most unique IPs

## Workflow
1) Identify log format (ssh auth? web auth? custom?)
2) Extract fields with:
   - grep + awk
   - Python (regex)
3) Count using:
   - sort | uniq -c | sort -nr
   - or Python Counter()

## Command patterns (fast)
- Unique usernames:
  - extract username → `sort | uniq | wc -l`
- Most common username:
  - extract username → `sort | uniq -c | sort -nr | head`
- Unique IPs per user:
  - extract user+ip pairs → group in python

## Tips
- Always validate extraction: print first 10 extracted lines
- Watch for "invalid user" vs normal logins
- Dates can include time zone / formatting differences
