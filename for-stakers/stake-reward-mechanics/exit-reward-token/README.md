---
description: Synthetic stable token
---

# EXIT Token \(in research phase\)

## **EXIT** Token

{% hint style="warning" %}
EXIT is an exploratory stable token. It incorporates an experimental design and may be introduced into the protocol at a later date. While it's face value is 1:1 with the US Dollar, the purchasing value is determined by the marketplace.  
  
**Terms, usage, protocols etc described below are a work in progress and are subject to change.**
{% endhint %}

The EXIT token is a stable synthetic ****currency whose face value is equivalent to the US Dollar \(1 EXIT token = $1 US Dollar\).

To mint EXIT, the protocol is over-collateralized with a 2nd token pegged to ETH. This "soft ETH" value is rebalanced regularly to correspond to ETH value  \(1 soft ETH = 1 ETH\). Soft Eth is maintained in the contract at a 2:1 ratio to the face value of EXIT. It is programmatically rebalanced to maintain this 2:1 ratio relative to the amount of EXIT minted by the protocol. 

The overcollateralization mechanism \(where there is always a 2:1 ratio of soft ETH to EXIT\) allows EXIT to be minted as a virtual stable token. In addition, the rebalancing can be called by any user at any time, decentralizing the process. 

As a stable token, EXIT has the equivalent virtual value to other USD stable coins. Users can trade and use EXIT as they would any other stable currency. 

## **EXIT Stability**

Stability hinges on two factors. 

1. **Face value of the token**: Face value is maintained in the contract at ~ $1.00 USD per EXIT. This price may vary based on the current ETH backing value; it is rebalanced every time a call is made to the PriceOracle. The soft ETH balance is adjusted at that time to maintain the virtual 2:1 peg.  
2.  **Exchange value of the token**: Exchange liquidity and supply/demand market forces determine the exchange value. If there is no liquidity for trading \(ie not enough DAI in an exchange to cover an EXIT trade\), then the value is capped by the amount of available liquidity.

{% hint style="info" %}
For example, if an individual wants to trade 1000 EXIT for 1000 DAI on [Uniswap](https://uniswap.exchange/), but there is only 500 DAI in the exchange, the user can either trade 500 EXIT for 500 DAI, or trade any amount over 500 for the same 500 DAI, effectively reducing the value. This issue occurs now with any stable trading pair when liquidity limits are reached.
{% endhint %}

{% hint style="success" %}
For more information on synthetic, stable commodities which informed this new model, please see:

* [https://www.basis.io/basis\_whitepaper\_en.pdf](https://www.basis.io/basis_whitepaper_en.pdf)
* [https://www.ampleforth.org/paper/](https://www.ampleforth.org/paper/)
{% endhint %}

