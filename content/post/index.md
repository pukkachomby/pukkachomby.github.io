# LATEST AT THE TOP (TO GET DATE)
| Date       | Title                        |
| ---------- | ---------------------------- |
| 2025-11-26 | [[thankgiving-reheating]]    |
| 2025-12-03 | [[gemini-in-brave]]          |
| 2025-12-10 | [[ai-prompting]]             |
| 2025-12-17 | [[macos-app-wishlist]]       |
| 2025-12-24 | [[apple-and-linux]]          |
| 2025-12-31 | [[gemini-flavors]]           |
| 2026-01-07 | [[air-fryer-eggs]]           |
| 2026-01-14 | [[brew-notes]]               |
| 2026-01-21 | [[best-musk-quotes]]         |
| 2026-01-28 | [[ai-humanizers]]            |
| 2026-02-04 | [[humanized-by-ai]]          |
| 2026-02-11 | [[block-the-bad-sites]]      |
| 2026-02-18 | [[the-perfect-diet]]         |
| 2026-02-25 | [[the-perfect-diet2]]        |
| 2026-03-04 | [[protect-kids-on-internet]] |
| 2026-03-11 | [[the-perfect-diet3]]        |
| 2026-03-18 |                              |
| 2026-03-25 |                              |
| 2026-04-01 |                              |
| 2026-04-08 |                              |
| 2026-04-15 |                              |
| 2026-04-22 |                              |
| 2026-04-29 |                              |
| 2026-05-06 |                              |
| 2026-05-13 |                              |
| 2026-05-20 |                              |
| 2026-05-27 |                              |
| 2026-06-03 |                              |
| 2026-06-10 |                              |
| 2026-06-17 |                              |
| 2026-06-24 |                              |
| 2026-07-01 |                              |
| 2026-07-08 |                              |
| 2026-07-15 |                              |
| 2026-07-22 |                              |
| 2026-07-29 |                              |
| 2026-08-05 |                              |
| 2026-08-12 |                              |
| 2026-08-19 |                              |
| 2026-08-26 |                              |
| 2026-09-02 |                              |
| 2026-09-09 |                              |
| 2026-09-16 |                              |
| 2026-09-23 |                              |
| 2026-09-30 |                              |
| 2026-10-07 |                              |
| 2026-10-14 |                              |
| 2026-10-21 |                              |
| 2026-10-28 |                              |
| 2026-11-04 |                              |
| 2026-11-11 |                              |
| 2026-11-18 |                              |
| 2026-11-25 |                              |
| 2026-12-02 |                              |
| 2026-12-09 |                              |
| 2026-12-16 |                              |
| 2026-12-23 |                              |
| 2026-12-30 |                              |

# DRAFTS
* air fryer breakfast
    * bacon?  pretty hard to mess that up tbh
    * 2 eggs in container, olive oil (or bacon fat), salt, cook @200 for 5m
        * or, old recipe
    * 1 potato in container, olive oil (or bacon fat), salt, cook @200 for 15m, flip cook for 12m.  if you overcrowd, repeat the last step.
    * toast. cook @200 for 6m
* iphone ai summary shortcut (test w honey's phone first)
* https://familyfocusblog.com/family-cleaning-schedule/
* https://familyfocusblog.com/51-tips-for-traveling-with-family/
* Ideas
    * https://www.scarymommy.com/
    * https://familyfocusblog.com/
* Styles
    * [Sassy](https://tinyurl.com/muhyref2)
    * [Family](https://familyfocusblog.com/51-tips-for-traveling-with-family/)
    * [Sassy+Family](https://tinyurl.com/c2fptawx)

# MAKING DATES SCRIPT
```python
import datetime

def get_wednesdays_of_2026():
    start_date = datetime.date(2026, 1, 1)
    first_wednesday = datetime.date(2026, 1, 7)
    current_date = first_wednesday
    wednesdays = []
    one_week = datetime.timedelta(days=7)
    while current_date.year == 2026:
        wednesdays.append(current_date.strftime('%Y-%m-%d'))
        current_date += one_week
    return "\n".join(wednesdays)

print(get_wednesdays_of_2026())

```
