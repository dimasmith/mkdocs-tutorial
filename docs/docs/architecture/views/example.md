# Implementation example

The system is implemented in Rust. Please implement common traits for your domain items where possible.

## Example

```rust title="src/domain/amount.rs"
#[derive(Debug, Clone, Copy, PartialEq)]
pub struct Amount(f64);

#[derive(Debug, Error)]
pub enum AmountError {
    #[error("Amount is negative: {amount}")]
    NegativeAmount { amount: f64 },
}

impl Amount {
    pub fn new(amount: f64) -> Result<Self, AmountError> {
        if amount < 0.0 {
            return Err(AmountError::NegativeAmount { amount });
        }
        Ok(Self(amount))
    }
}

impl TryFrom<f64> for Amount {
    type Error = AmountError;

    fn try_from(value: f64) -> Result<Self, Self::Error> {
        Amount::new(value)
    }
}
```
