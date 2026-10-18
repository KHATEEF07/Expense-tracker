# 💸 Khateef’s Expense Tracker

A lightweight command-line expense tracker built by **Khateef** with Python and SQLite. No external dependencies to run — just Python 3.8+.

## Features

- Add, edit, and delete expenses
- Filter by category or month
- Monthly summary with spending breakdown by category
- Export all data to CSV
- Fully tested with `pytest`

## Installation

```bash
git clone https://github.com/YOUR-USERNAME/expense-tracker.git
cd expense-tracker
pip install -r requirements.txt   # only needed for running tests
```

## Usage

```bash
python -m expense_tracker add 12.50 food -d "Lunch with team"
python -m expense_tracker add 45 transport --date 2026-03-10
python -m expense_tracker list
python -m expense_tracker list -c food -m 2026-03
python -m expense_tracker edit 1 --amount 14 --category dining
python -m expense_tracker delete 2
python -m expense_tracker summary -m 2026-03
python -m expense_tracker export my_expenses.csv
```

Example summary output:

```
Summary for 2026-03
  rent             600.00  (80%)
  food             100.00  (13%)
  transport         45.00  (6%)
  TOTAL            745.00
```

Data is stored in `~/.expense_tracker.db`. Use `--db path/to/file.db` to change it.

## Project structure

```
expense_tracker/
  db.py       # SQLite storage layer (CRUD, summaries, CSV export)
  cli.py      # argparse command-line interface
tests/
  test_db.py  # unit tests
```

## Running tests

```bash
pytest
```

## Roadmap

- [ ] Monthly budgets with overspend warnings
- [ ] Charts with matplotlib
- [ ] Flask web UI / REST API
- [ ] Recurring expenses

## Author

**Khateef**

## License

MIT — see [LICENSE](LICENSE).
