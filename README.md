# Custom Validators in Angular Reactive Forms

## Overview

This example demonstrates how to implement custom validators for Angular Reactive Forms, including email validation, password validation, numeric range validation, and built-in form validators.

## Features

- **Required Fields:** Ensures mandatory fields are not empty.
- **Length Validation:** Validates minimum and maximum character lengths.
- **Email Validation:** Checks whether an email address matches the expected format.
- **Password Validation:** Requires a password between 6 and 100 characters containing at least one number.
- **Range Validation:** Validates numeric values against a specified minimum and maximum.

## Implementation

### Reactive Form

```typescript
this.reactiveForm = this.formBuilder.group({
    first_name: ['', [
        Validators.required,
        Validators.minLength(3),
        Validators.maxLength(50)
    ]],
    last_name: ['', [
        Validators.required,
        Validators.minLength(3),
        Validators.maxLength(50)
    ]],
    phone: ['', [
        Validators.required,
        ValidationService.checkLimit(5000000000, 9999999999)
    ]],
    email: ['', [
        Validators.required,
        ValidationService.emailValidator
    ]]
});
