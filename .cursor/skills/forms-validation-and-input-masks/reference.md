# Forms Validation and Input Masks Reference

## Minimum Validation Matrix

- Required: simple and direct message
- Invalid format: explain expected format
- Minimum/maximum length: state the limit
- Remote error (`422`): map to field or global error

## Message Pattern

- short, objective, no technical term
- one message per field at a time
- prioritize the most critical error first

## Submit Checklist

1. button disabled when invalid
2. loading during submission
3. avoid double submit
4. success with clear feedback
5. failure with correction/resubmission path
