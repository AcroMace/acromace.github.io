---
title: Less Degenerate Guide to Options
permalink: /less-degenerate-options
---

<div class="alert alert-warning" role="alert">
  Disclaimer: I am not a financial advisor. This is mostly a summary of what I learned on the internet for me to refer to in the future. Options can blow up your account if you're not careful. Do not yolo your retirement money and end up like the people on <a href="https://www.reddit.com/r/wallstreetbets">/r/wallstreetbets</a>.
</div>

## Options

Options can be used as **insurance** for your positions (ex. in case of a stock market crash) for less degenerate investors, or a **leveraged bet** (ex. an all or nothing bet to 10x your money or lose it all) for more degenerate "investors."

Options can be described by four properties

- [Underlying](https://www.investopedia.com/terms/u/underlying-option-security.asp): the stock, ETF, etc. that you're betting on or providing insurance for. I'll just assume the underlying is a stock to make reading less confusing.
- Expiration: the day the option expires
- Strike: the price of the stock at which the option is worth something on expiration
- Call or put: the two types of options, explained below

For example, a call option on the stock $MEME that expires June 9th at a strike price of $420 could be written

<div class="ascii-diagram">
MEME 6/9 420c
</div>

The price of the option is called the **premium**, just like the premium you pay for insurance.

## Call

A call is a **bet** that a stock (or whatever your underlying) will **go up**.

For a stock $MEME, a call option with a strike price of $420 means that the option price at expiration would increase by $100 for every dollar $MEME goes over $420.

- If $MEME is $421 when the option expires, then the option would be worth $100.
- If $MEME is $422 when the option expires, then the option would be worth $200, etc.

However, if $MEME is $420 or less on expiration, the call option would be worth $0.

<div class="ascii-diagram">
$MEME call price at expiration = 100 * ($MEME price at expiration - strike price)
or $0 if $MEME price is less than or equal to the strike price
</div>

The option price at expiration is the **[intrinsic value](https://www.investopedia.com/terms/i/intrinsicvalue.asp)** of the option. It's based entirely on the difference between the price of the stock and the strike price.

If the intrinsic value of the stock is positive, or the price of the stock is greater than the strike price (i.e. $MEME is worth more than $420, the strike price), then the option is said to be **in-the-money** (**ITM**).

If the price of the stock is less than the strike price (i.e. $MEME price < $420), then the option is **out-the-money** (**OTM**). If the price is at the strike price (i.e. $MEME price = $420), then the option is **at-the-money** (**ATM**).

## Put

A put is a **bet** that the stock will **go down**.

For a stock $MEME, a put option with a strike price of $420 means that the premium at expiration would increase by $100 for every dollar $MEME goes under $420.

- If $MEME is $419 when the option expires, then the put would be worth $100.
- If $MEME is $418 when the option expires, then the put would be worth $200, etc.

If $MEME is $420 or more on expiration, the put option would be worth $0.

<div class="ascii-diagram">
$MEME option price at expiration = 100 * (strike price - $MEME price at expiration)
or $0 if $MEME price is greater than or equal to the strike price
</div>

This can be used as insurance against a bullish position. For example, if you have SPY shares, you can buy SPY puts to hedge against the possibility of a market crash.

The ITM/OTM direction is the opposite for puts.

- MEME 420p is ITM if $MEME price is less than $420
- MEME 420p is OTM if $MEME price is greater than $420

## Exercising and leverage

When you buy a call option, you're buying the option to buy [100 shares of a stock](https://www.investopedia.com/terms/l/lot.asp) at the strike price. If you choose to buy the shares, you'd be **exercising** the option.

For example, if you exercise a MEME 420c, then you're buying 100 shares of $MEME for $420 each, and thus spending $42,000 for them all. If $MEME moons to $1000, then you'd be buying the stocks worth $1,000 for $420 each. If it was less than $420, you'd probably choose not to exercise it, and the option would expire worthless.

Conversely, when you buy a put option, you're buying the option to sell 100 shares of a stock at the strike price. If you buy a MEME 420p, then $MEME plunges to $200, you'd still be able to sell 100 shares of $MEME to someone at $420 each.

Options are considered **leveraged** since the price could increase up to $100 for every dollar the stock price goes past the strike price. In other words, options have **up to 100x leverage**.

This is why if an option price is $0.42, you pay $42 to buy it (100 * $0.42). You're paying for a right to exercise on 100 shares.

## Breakeven

If you buy an option, you had to pay the price for whatever the option was worth (the premium). This means that if the option is worth $0, then you actually lost money, since you also paid the premium to own something worthless.

The **breakeven** is the price at which you don't lose any money. Basically, you need the price of the stock to go past the strike price by enough to cover the price you paid for it.

For example, if you have a MEME 420c, and you paid $500 for it, then you'd need $MEME to be at least $425 on expiration in order to cover the cost you paid for it, since then you'd be able to sell the option for $500.

Similarly, if you have a MEME 420p, and you paid $500 for it, then you'd need $MEME to be at most $415 on expiration to not lose money.

<div class="ascii-diagram">
Call
        Strike      Strike + premium
         $420            $425
<----------|---------------|++++++++++++++++++++++++++>
    LOSS       LOSS    Breakeven        GAIN

Put
               Strike - premium       Strike
                    $415               $420
<+++++++++++++++++++++|------------------|------------>
          GAIN    Breakeven    LOSS          LOSS
</div>

## Extrinsic value

The **intrinsic value** only considers the strike price and the price of the stock.

The **[extrinsic value](https://www.investopedia.com/terms/e/extrinsicvalue.asp)** is what makes up the rest of the premium. In general, the more likely a stock is to go in-the-money, the more you have to pay for it.

- **Time**: if you have a long dated option (the expiration date is further out), then it's more likely to go ITM. Therefore the premium increases with a longer expiration date.
- **Volatility**: if the stock is volatile (it's expected to have large movements in price), then it's more likely to go ITM at some point before the expiration. Therefore the premium increases with volatility.

## The Greeks

The [Greeks](https://www.youtube.com/watch?v=GxmIvvROge4) describe the factors (like time and volatility) that determine the premium of an option. You don't have to know these exactly, but understanding the general correlation is useful.

- **Delta** (Δ): The change in the premium for a $1 **change in the price** of the stock. If delta is 0.42, then the option price increases by $42 when the stock goes up by $1.
- **Gamma** (Γ): The **change in delta** for a $1 change in the price of the stock. If delta is 0.42, and gamma is 0.1, then delta would increase to 0.52 if the stock goes up by $1.
- **Theta** (Θ): The change in the premium after a day (i.e. **time decay**). If theta is -0.42, the premium would decrease by $42 the next day.
- **Vega** (v): The change in the premium for a 1% change in **implied volatility**. If vega is 0.42, the premium would increase by $42 if implied volatility goes up by 1%.
- **Rho** (p): The change in the premium for a 1% chance in **interest rates**. If rho is 0.42, the premium for a call option would increase by $42 if interest rates went up 1% (decreases for put options). Generally irrelevant.

The Greeks are used in the [Black Scholes model](https://www.investopedia.com/terms/b/blackscholes.asp) for finding the options price.

## Greeks implications

These are mostly just implications for degenerate trades based on the Greeks

### Closeness to the money

- **Premium close to the money**: Since delta increases the closer you get to the money, the more premium you'll have to pay if the strike price is near the current price of the stock.
- **Far out the money options**: Same as above, but this means that options with a strike price very far from the current price is worth very little. Something people on WSB do is buy these options since they're very cheap in hopes of a huge movement in the stock price that brings the option closer to the money (i.e. stock price closer to the strike price). In this case, you'd see a much bigger gain since the option was previously worthless, and you'd be rich. In most cases, they're cheap for a reason, and you lose money.

### Time

- **Long-dated options**: Theta (time decay) increases with time. That is, the closer the option is to expiring, the faster the option will lose value. This is why non-degenerate people try to buy options with a long expiry date, which makes theta less of a factor.
- **Short-dated options**: On the other hand, WSB people play weeklies (options that expire in a week) since they're much cheaper. It also means there's less extrinsic value (due to time), so any movement in price is much more visible in the premium. In most cases, it just means you hold your options until they expire worthless.
- **LEAPS**: You can also buy options with an expiry date longer than a year, [long-term equity anticipation securities (LEAPS)](https://www.investopedia.com/terms/l/leaps.asp) to get the leverage of options without being affected by theta as much. These are pretty expensive.
- **Theta gang**: People [sell options](https://www.investopedia.com/articles/optioninvestor/09/selling-options.asp) as a way to benefit from the time decay. In this case, you sell an option, then watch as the option loses value as time passes, then buy it back for cheap to close out your position.

### Volatility

- **Meme stocks**: Because volatility is high on meme stocks, it's super expensive to buy options for them. This makes it harder to earn a profit even if the meme stock moves in your direction since the initial cost was so high.
- **IV crush**: Around important events like earnings, volatility increases since there's more unknowns on how the market will react to the event. After the event, volatility decreases substantially. This means that if you try to play earnings with options, you could buy an expensive option and see the premium plummet right after earnings, even if the stock moved in the direction you wanted.
- **Spreads**: Explained below, but using spreads can decrease the effect of changes in volatility on your position.

## Debit spreads

Instead of buying just single options, you could both buy *and sell* options to change the risk/reward of your position. In general, you decrease the total amount of money you can earn in order to decrease the total amount of money you could lose.

### Call debit spread

For a call debit spread, you purchase a call closer to the money, and sell a call further from the money.

For example, you could buy a MEME 420c for $200 and sell a MEME 430c for $100. Then, you'd have paid $100 total to enter this position.

- If $MEME < $420 on expiration, then both of your options are worthless, and you lose $100. This is better than $200 you would have lost for just buying MEME 420c.
- If $MEME = $425 on expiration, then the MEME 420c is worth $500 and MEME 430c is worthless. In this case, you made $400 ($500 - $100 premium paid). This is better than the $300 you would have made by just buying the MEME 420c.
- if $MEME = $435 on expiration, then MEME 420c is worth $1500 and MEME 430c is worth $500. Since you sold the MEME 430c, your -1 position of MEME 430c is a loss of $500 to you, and your two calls together is worth $1000. With the $100 in premium you paid, you earned $900. This is worse than the $1300 you would have earned ($1500 - $200) if you only bought the MEME 420c.

Basically, you **decreased the breakeven price** from $422 to $421, and **decreased the max loss** from $200 to $100. In return, you **capped your max profits** to $900 if $MEME increases past $430, the strike price of the call you sold. Your profits will increase as normal as $MEME increases from $421 to $430, then stay the same from then on.

<div class="ascii-diagram">
Call debit spread
                                   $430
                                  +|++++++++++++++>
                               +++ Sold strike
     Bought strike          +++
         $420      $421  +++
<----------|---------|+++
  Bought strike     Breakeven
</div>

### Using a call debit spread in earnings

Using a spread is **helpful in high volatility environments**. Let's say that the Meme company is having their earnings tomorrow, expectations are high, and the stock is expected to make huge swings in price. Because of the increased volatility, MEME 420c is now $1,100, and MEME 430c is $1,000.

Buying a MEME 420c by itself (i.e. a **naked call**) would be very expensive. However, if you buy a MEME 420c for $1,100, then sell a MEME 430c for $1,000, then you've only paid $100 for the premium, while having the exact same payoff as above, where MEME 420c was $200 and MEME 430c was $100.

With just MEME 420c, your breakeven was $431, because of the high price. With the call debit spread, your breakeven was lowered to $421. Your max loss also went from $1100 with a naked call to just $100.

Let's say that after earnings, $MEME increases from $400 to $425. However, volatility has been crushed, and no further movements in the stock price is expected before your option expires. Then, MEME 420c would now be worth $500. If you just bought MEME 420c, then you were right in the direction of the movement, but $MEME just *didn't move enough in the direction you predicted given the high premium*. Since you paid $1,100 for the option, you lost $600.

However, if you bought a call debit spread, then the 430c you sold just became worthless, and you earned $1,000. Now, instead of losing $600, you earned $400 ($500 for 420c - $0 for 430c - $100 paid in premium).

This seems like a clearly better choice, but the catch is that the cap in profits hurts if the stock shoots up way higher than anyone expected. If $MEME shoots to $500, then the 420 would have been worth $8,000 (100x leverage on $500-$420), and you would have earned $6,900 ($8,000-$1,100). With the call debit spread, your profits are the same as if the price increased to $430, and you earn $900.

### Put debit spread

For a put debit spread, you buy a put closer to the money, and sell a put further out the money.

This is just the put equivalent of a call debit spread.

For example, you could buy a MEME 420p for $200 and sell a MEME 410p for $100.

- If $MEME > $420 on expiration, you lost $100 (max loss)
- If $MEME = $415 on expiration, you gained $400 ($500 for MEME 420p - $0 for MEME 410p - $100 for net premium paid)
- If $MEME ≤ $410 on expiration, you gained $900 (max gain)

<div class="ascii-diagram">
Put debit spread
                             $419        $420
                            +++|-----------|-------------->
                         +++  Breakeven   Bought strike
                      +++    GAIN         LOSS
             $410  +++
<++++++++++++++++|+
            Sold strike
</div>

## Theta Gang

Options are a zero sum game. For someone to win money, someone else must lose money. Since most people on WSB buy options with low likelihood of making money and then lose money, that must mean someone else must be collecting all the money that's lost.

Theta Gang sells options with a low probability of profit, then profits as the option becomes worthless with time.

### Pros

- More likely to earn a steady profit over time
- Time is on your side - you don't have to worry about owning a quickly depreciating asset
- You profit when a stock moves sideways (when there's no movement)
- Even when a stock moves in the opposite direction you want, you still have the premium you earned as a buffer

### Cons

- You know your max profit when you open a position. You won't have anything suddenly 10x in value, so it's much more boring.
- In general, you have a series of small wins but the losses if a position turns against you can be huge. You can wipe out the gains of ten wins in a single play that goes wrong.
- If you are over-leveraged and the market moves against you, your entire portfolio could be wiped at once (vs. just owning stocks). People who work with spreads tend to only invest a certain percentage of their portfolio in case all of their positions are closed as losses.

## Betting with stocks vs. options

Options

- Higher leverage and risk = higher potential gains
- More entertaining
- Higher tax for frequent short-dated trades, but can use Section 1256 options for lower short-term tax rates (see below)

Stocks

- Less likely to blow up your account (when not using margin)
- Likely more profitable if you just buy and hold index funds
- Less work - just buy and hold
- Lower tax rate if you just buy and hold to get capital gains tax

I like having a small options portfolio that I actively manage but have most of my non-degenerate portfolio in index funds. This removes the temptation to actively manage the majority of my money since most people underperform indices, while still giving short term dopamine boosts in the small portfolio.

## Random technicalities and terminologies

### Order types

These are just shorthands for opening and closing options positions.

Buying options

- **BTO**: buy to open
- **STC**: sell to close

Selling options (theta gang)

- **STO**: sell to open
- **BTC**: buy to close

### [American vs. European options](https://www.investopedia.com/articles/optioninvestor/08/american-european-options.asp)

American options can be exercised at any time. European options can only be exercised at expiration. [This mostly matters if you try to do more complex strategies](https://www.marketwatch.com/story/trader-says-he-has-no-money-at-risk-then-promptly-loses-almost-2000-2019-01-22).

### [Section 1256 options](https://www.forbes.com/sites/greatspeculations/2019/05/30/trading-futures-other-section-1256-contracts-has-tax-advantages/?sh=10bb015b1f80)


<div class="alert alert-warning" role="alert">
  Disclaimer: I am not a tax advisor. Talk to a tax advisor.
</div>

[Options on regulated futures contracts count as a 1256 contract](https://www.forbes.com/sites/greatspeculations/2019/05/30/trading-futures-other-section-1256-contracts-has-tax-advantages/?sh=40ce50881f80), which allows the gains to be taxed at 60% long-term capital gains rates and 40% at short-term rates, vs. normal contracts where anything held less than a year is taxed at 100% short-term rates.

Specifically, options on SPY (the ETF tracking the S&P 500 index) would be taxed at normal income tax rates when the position is closed in less than a year. SPX, the futures version of SPY, would be considered a Section 1256 option and be taxed more favourably.

[You can read more about taxes on options in general here](https://www.investopedia.com/articles/active-trading/053115/tax-treatment-call-put-options.asp).
