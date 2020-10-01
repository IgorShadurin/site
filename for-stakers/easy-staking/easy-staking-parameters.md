# EasyStaking Parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Value - Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Front-end Application</td>
      <td style="text-align:left"><a href="https://easy-staking.xdaichain.com/">https://easy-staking.xdaichain.com</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Minimum STAKE Deposit</td>
      <td style="text-align:left">10^-18 (0.000000000000000001 STAKE)</td>
    </tr>
    <tr>
      <td style="text-align:left">Maximum STAKE Deposit</td>
      <td style="text-align:left">No Maximum</td>
    </tr>
    <tr>
      <td style="text-align:left">Instant Withdrawal Fee</td>
      <td style="text-align:left">2%* + ETH gas fees</td>
    </tr>
    <tr>
      <td style="text-align:left">Instant Withdrawal Availability</td>
      <td style="text-align:left">STAKE returned to wallet immediately</td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Fee</td>
      <td style="text-align:left">
        <p>0% + ETH gas fees. Requires 2 transactions:</p>
        <p>1. Prepare withdrawal.
          <br />2. Process during the scheduled withdrawal window.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Availability</td>
      <td style="text-align:left">12 hours* after request, funds are available to withdraw during the scheduled
        withdrawal window (also 12 hours*). STAKE price is the price when withdrawn,
        not the price when withdrawal is scheduled.</td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Window</td>
      <td style="text-align:left">12 hours*. Scheduled withdrawals are available to pull within this time
        period. If not withdrawn, they are returned to the protocol. <b>APR is not reset if returned</b>,
        funds continue to accrue emissions as before.</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking APR</td>
      <td style="text-align:left">Up to 15% APR based on 2 factors:
        <br />1. Amount of time STAKE is locked in protocol (up to 7.5% based on a
        <a
        href="https://www.desmos.com/calculator/2xtimbnzqw">sigmoid function</a>). Sigmoid parameters*: a = 75000000000000000, b =
          0, c = 10000000000000.
          <br />2. STAKE <code>totalSupply</code> multiplied by <code>totalSupplyFactor</code> (which
          is 50%*), and the total amount staked by all participants. Up to 7.5%,
          based on a <a href="https://github.com/xdaichain/easy-staking-contracts/blob/d5a477e4faf83d33901737cb461e97954ac4c1ec/contracts/EasyStaking.sol#L440">linear function</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left">Multiple Deposits</td>
      <td style="text-align:left">Supported. <b>Each deposit event creates a new deposit ID</b>. You can
        manually add additional STAKE to a current deposit using the <a href="https://github.com/xdaichain/easy-staking-contracts/blob/d5a477e4faf83d33901737cb461e97954ac4c1ec/contracts/EasyStaking.sol#L223"><code>deposit(uint256 _depositId, uint256 _amount)</code></a> function
        of the EasyStaking contract. UI doesn&apos;t support replenishing existing
        deposits but allows the staker to create multiple deposits. Emission is
        accrued from time of deposit for each ID.</td>
    </tr>
    <tr>
      <td style="text-align:left">Partial Withdrawals</td>
      <td style="text-align:left">Supported. User can withdraw a partial amount from any deposit, and will
        receive the withdrawal amount + APR calculated at time of withdrawal. The
        remaining deposit amount will continue to accrue APR from that point forward.</td>
    </tr>
    <tr>
      <td style="text-align:left">Pending Withdrawal</td>
      <td style="text-align:left">A withdrawal has been scheduled for a deposit. The window to process the
        withdrawal is not yet open.</td>
    </tr>
    <tr>
      <td style="text-align:left">Ready to Withdraw</td>
      <td style="text-align:left">The withdrawal window is open and a scheduled withdrawal is available
        for processing. This occurs after 12 hours and eligibility remains for
        12 hours. Users can enter the amount to withdraw and claim.</td>
    </tr>
    <tr>
      <td style="text-align:left">Current STAKE Price</td>
      <td style="text-align:left"><a href="https://api.coingecko.com/api/v3/simple/price?ids=xdai-stake&amp;vs_currencies=usd">https://api.coingecko.com/api/v3/simple/price?ids=xdai-stake&amp;vs_currencies=usd</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Github Repository</td>
      <td style="text-align:left"><a href="https://github.com/xdaichain/easy-staking-contracts">https://github.com/xdaichain/easy-staking-contracts</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">EasyStaking Contract</td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad">0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">LP Distribution Contract</td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li><a href="https://etherscan.io/address/0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d">0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">STAKE Token Contract</td>
      <td style="text-align:left"><a href="https://etherscan.io/token/0x0ae055097c6d159879521c384f1d2123d1f195e6">0x0ae055097c6d159879521c384f1d2123d1f195e6</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">LP Distribution Time</td>
      <td style="text-align:left">LP rewards distributed on average every 7 days.</td>
    </tr>
  </tbody>
</table>

_\*configurable_

{% hint style="warning" %}
Current parameters subject to change.
{% endhint %}

