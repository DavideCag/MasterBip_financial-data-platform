# Design Decisions

## Language Choice

- C++: used for performance-critical aggregation logic
- Python: used for flexible validation and testing

## Data Format

- Input: CSV
- Output: JSON

Reason:
- CSV is common for financial transactions
- JSON is easy to validate and integrate with services

## Error Handling

We introduced:
- invalid_lines counter
- strict validation rules

This ensures robustness in presence of malformed data.

## Min/Max Logic

Minimum value is initialized dynamically using the first valid input
to avoid incorrect comparisons with default values.