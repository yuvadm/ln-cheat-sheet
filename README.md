# Lightning Network ⚡ Cheat Sheet

Everything you need to work with the Lightning Network in a dense and concise form.

## Channels

- **Local balance**: outgoing liquidity
- **Remote balance**: incoming liquidity

Payments are attempted in two phases:

- Pathfinding: traversing the channel graph and finding a path to the destination node
- Routing: attempting to actually send funds on a given path.

Public graph information includes channel capacity and fees, and is known in **path finding** phase.

Private graph information includes the current liquidity balance, and can only be discovered if a payment succeeds or fails on a **routing** attempt.

### Circular Rebalance

Excess **local** balance on one channel is used to pay _yourself_ with funds coming in on another channel with excess **remote** balance.

At least two peers (i.e. two separate channels) are needed for a rebalance to occur.

### Fees

Fees are always charged on the **outgoing** path, when a payment is **forwarded**.

## Numbers

### Definitions

```
1 sat (satoshi)          = 1 / 100,000,000 = 0.00000001 BTC
1 ppm (part per million) = 1 /   1,000,000
1 bps (basis point)      = 1 /      10,000
1 %   (percent)          = 1 /         100
```

### ppm to %

```
1    ppm = 0.0001%
10   ppm =  0.001%
100  ppm =   0.01%
1000 ppm =    0.1%
```

### ppm to bps

```
1000 ppm = 1 bps
```

### bps to %

```
1   bps = 0.01%
10  bps =  0.1%
100 bps =    1%
```
