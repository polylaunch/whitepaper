# Polylaunch Protocol v0.0

_Abstract_

The Polylaunch Protocol enables permissionless and accountable on-chain fundraising. By giving supporters oversight on a project team’s capital management, we ensure that teams publicly raising funds for crypto projects show greater accountability towards the people funding them. Polylaunch introduces a new financial instrument called a **Venture Bond**, a functional Non-Fungible Token (NFT) integral to all launches on the protocol. When a project initiates a Polylaunch, their supporters can send funds into the Polylaunch contract to purchase the tokens on offer. After a sale is successfully completed, supporters are able to mint a Venture Bond, entitling them to a constant stream of the project tokens over time and sale governance rights. Capital raised by the project team is also streamed over time, and this stream can be accelerated to fund faster development, but can also be democratically revoked by venture bond holders who are then refunded. Polylaunch provides a powerful new way for crypto investors to manage their risk while showing their support for early stage projects, both for supporters who contribute directly to the launch, and those who purchase project tokens or venture bonds on the secondary market.

**Keywords:** Polylaunch, NFT, Venture Bond, DAICO, fundraising, $PL, DeFi

## 1   Problem

Blockchains and consensus networks have created a new mechanism for transferring value between economic agents. Bitcoin deployed the first trustless peer-to-peer electronic cash system in 2009 ([Nakamoto 2008](https://bitcoin.org/bitcoin.pdf)), and Ethereum extended this concept to support smart contracts, generalized scripts enabling developers to write and deploy computer programs that could, among other things, hold and transfer money according to programmed conditions ([Buterin 2013](https://ethereum.org/en/whitepaper/)). These advancements underpin an emerging paradigm shift in human economic activity and social / economic coordination. 
   
These consensus technologies were founded to improve upon an inefficient, exclusive and self-destructive financial system. Permissionless public blockchains are, by design, effectively unkillable and impossible to censor. While this does represent a significant improvement on trust-based financial architectures, it also brings significant challenges. The permissionless nature of these networks, coupled with a convergence of social, technical and economic factors, has led to an ecosystem rife with scammers, fraud, market manipulation. Unscrupulous actors recognized the potential of unregulated and speculation-driven markets; one study estimates that 11% of funding raised in “Initial Coin Offerings” (ICOs) conducted during the 2017 bull cycle went to scam projects. Additionally, even well-meaning project founders raising funds were irresponsible or proved unable to deliver on the promise upon which they raised capital, with the same study estimating that 19% of funding raised in ICOs during the 2017 bull cycle went to dead or failing projects. ([Satis Group, 2018](https://research.bloomberg.com/pub/res/d28giW28tf6G7T_Wr77aU0gDgFQ))

Today, an abundance of launchpads have emerged, enabling project teams to launch token sales similar to the ICO’s of 2017, with, in many cases, similar outcomes. There are some which aim to limit their user’s risk exposure by providing a more curated experience, but this sacrifices the open and permissionless spirit of the Web3 ecosystem.

To resolve these issues and bring fairness, transparency and accountability to decentralised permissionless project funding, we built the Polylaunch Protocol, building upon the foundation of the Decentralized Autonomous Initial Coin Offering (DAICO) concept [first proposed](https://ethresear.ch/t/explanation-of-daicos/465) by Vitalik Buterin in January 2018. 

With Polylaunch, teams and investors have on-chain capital management and governance, affording investors confidence that their funds will only be accessible by teams that show development progress and providing teams the credibility of a fairly launched, transparent token offering. Polylaunch brings verifiable trust to decentralised fundraising. 


## 2   Roles

### 2.1   Launchers

Launchers are project teams or individuals raising funds. They will be honest projects aiming to raise capital from their community to fund development in a way that enables supporters to ensure accountability. The best development teams in the community will opt to conduct token sales using Polylaunch because it will attract more informed and engaged investors, confident that manipulation and rug pulling is unlikely. 

### 2.2   Supporters

Supporters are individuals sending funds to the Polylaunch contract to fund a launcher. The risks that crypto investors are exposed to mean that they have huge incentive to support projects running Polylaunches. Normally, scam projects are able to raise significant capital even from sophisticated investors by putting together credible-looking plans and marketing collateral. Other projects start out with good intentions, but rapidly fail, leaving the investor without recourse or ability to apply ongoing oversight. Polylaunch solves these problems for supporters.

## 3   Anatomy of a Polylaunch

The first type of Polylaunch offered is the bond launch. Developers configure and deploy their launch by providing parameters specifying the details of the launch to the smart contract, including **duration**, **soft cap** (minimum raise), **hard cap** (maximum raise), **price mechanism**, **start time**, **end time**, and **initial flow rates** for the launch team and the supporters. A flow rate is the rate at which users can withdraw their funds (sale token for the supporters, USD for the launchers) after the sale is completed. Launchers are streamed their raised funds over time rather than receiving them all at once, and supporters can vote to put the launch contract into refund mode and proportionally get back the raised funds if they see fit. 

Supporters contribute to the launch using a stablecoin such as DAI or USDC. If the soft cap is reached prior to the sale end time, the launch is successful. Once the end time of the sale is reached, each contributor can claim a **venture bond**, which is a non-fungible token denoting specific privileges to the holder throughout the life of the launch contract. A venture bond is a new type of financial instrument that receives a stream of project tokens, redeemable by the venture bond holder at any time. The venture bond contracts are a modified fork of the Zora Protocol’s cryptomedia primitive ([Zora 2021](https://zora.engineering/whitepaper)).


### 3.1   Venture Bonds

Venture bonds hold the following key parameters:


| Parameter |  Definition | Fixed/Variable State |
| --- | --- | --- |
| Voting Power | Equal to the total number of tokens bought in the sale. Dictates the weighting applied to a venture bond holder’s vote. | Fixed |
| Tappable Balance | Total number of remaining tokens the venture bond holder can claim. | Variable |
| Flow rate | The rate at which the venture bond receives the sale token. | Variable |
| Last Withdrawn Time | The last time funds were tapped from the venture bond. | Variable |
| ERC721 NFT parameters | Token URI, Content Hash, Metadata URI, Metadata Hash. A venture bond can behave as a collectible NFT. | Fixed |

For particularly risk averse individuals, obtaining a Polylaunch project’s venture bond, either by contributing to a Polylaunch or buying one on the secondary market, represents a safer way to gain exposure to the project without the risks normally associated with purchasing a crypto asset. Holding a venture bond entitles the holder to a steady stream of the underlying asset, and also provides the security of being part of the project’s governance and being eligible for a refund in the event that the project severely underperforms. 

Even for those who do not hold a venture bond, due to the existence of the venture bond holders they can have extra confidence in the project than what is typical, safe in the knowledge that the project cannot run away with all of the raised funds. As well as the key parameters listed above, each venture bond also has its own embedded market that allows a supporter to manage the market for their bond, enabling them to set, receive, accept and reject bids. 

Venture bonds also hold value as collectibles. We have programmed the ability for launchers to make a subset of their venture bonds limited edition, with unique artwork and metadata for each one so that one day owners may have a valuable artifact from the very first investment round of the Googles and Apples of Web3 - even after all project tokens have been withdrawn and the Polylaunch process has completed. 


## 4 Governing a Polylaunch

During the course of a project life cycle, two governance events can occur: 

1. **Increase flow rate:** Launchers can request to increase their flow rate, enabling them to withdraw more funds in a given period and therefore shortening the total withdrawal process. This might occur if developers want to hire more talent, for example. Venture bond holders are incentivised to vote as their project token flow rate increases each time they vote on a proposal.

2. **Refund:** Supporters can propose that venture bond holders are refunded, revoking invested capital from the Polylaunch contract. This governance event puts a Polylaunch project into “refund mode”, which allows venture bond holders to claim refunds on all of the USD left in the contract. Each refund issued is proportional to the user’s tappable balance and wallet balance, with the maximum amount being bounded by their voting power. Only venture bond holders are refunded. This prevents a malicious launch team from gaining most of the refund via tokens they own which were not available in the sale.

The Polylaunch Protocol brings a new layer of oversight to the governance of capital raised for a project, giving both supporters and development teams confidence that incentives are aligned. Funds will be available to sustain launchers as they build, but are not guaranteed if they stop delivering. Moreover, the possibility of a refund vote means that the fungible tokens offered are not just backed by speculation as we see today - they are additionally backed by the stablecoin value raised in the launch. 

## 5 PolyVault

Any given Polylaunch contract will have a pool of USD at its disposal while the vesting periods pass. During this period it is beneficial to all parties that the funds are put to work to gain interest or yield in a secure manner. By integrating with interest-bearing DeFi protocols we provide a way for launchers to safely earn on their balances as they vest.

The USD locked in a Polylaunch contract can be deposited into a PolyVault associated with the Polylaunch. Once in a PolyVault, the funds are sent to an interest bearing pool provided by a supported DeFi protocol specified by the launcher. While inside a vault, the launcher is still able to tap their funds as normal, allowing remaining funds to continue to gain interest. When funds are moved out of a vault, a portion of the interest is taken by the Polylaunch protocol and distributed to $PL holders. Note that PolyVaults are optional - in the case that a launcher is especially risk averse they can just leave their funds locked in the Polylaunch contract.

Methods to utilise the project tokens as well as the USD, for example, placing them in a liquidity pool, are still being considered. However, in the current state of DeFi deploying funds in this manner is inadvisable as it exposes the project funds to impermanent loss, and when combined with the fund streaming  mechanism, leads to additional complexities.

### 5.1 PolyVault Registry

The PolyVault Registry is where the Polylaunch developers will provide information of interest bearing protocols and specific pools/vaults that PolyVault can interact with, as Polylaunch is upgradeable the number of supported protocols and pools/vaults can and will increase. The parameters for a registered vault are shown in the table below:

| **Parameter** | **Data Type** | **Definition** |
| --- | --- | --- |
| `vaultId` | `uint256` | The unique identifier for the specific interest bearing pool/vault to deposit funds to. A launcher will include the vault ID when depositing funds to a PolyVault. |
| `vaultContractAddress` | `address` | The contract address associated with the interest bearing pool/vault |
| `vaultDesignation` | `string` | String representation of the protocol and pool/vault for UX. |
| `vaultProvider` | `uint256` | The unique identifier for the protocol that hosts the pool/vault, e.g. All pools from Compound Protocol will have vaultDesignation 1. |
| `vaultActive` | `bool` | The developers can choose to remove support for a pool/vault by deactivating it (this will not affect funds already deposited into that pool/vault). |

The currently supported interest bearing protocols on Ethereum Mainnet are Compound Lending Pool, Yearn Finance yVaults v2 and Aave V2 Lending Pools; these are allocated vaultDesignation 1, 2 and 3 respectively. Since each protocol can support multiple USD stablecoins these will be represented by different vault IDs. As the Polylaunch protocol moves to new blockchains, support will be added for the appropriate and available interest-bearing protocols on that blockchain and, where possible, cross-chain PolyVaults will also be supported.

## 6 $PL Token

Polylaunch Protocol is accompanied by the $PL token. $PL is a governance token for the protocol that also entitles holders to a cut of fees generated by the protocol if the holder is delegating their vote (including self-delegation).

**Fees:** Programmed within each venture bond is a fee structure for all sales of the bond. A small percentage goes to the protocol and the rest to the bond owner that is selling. The percentage that goes to the protocol is sent to $PL holders. Holders will also be eligible to receive a percentage of the yield generated by the locked USD.

**Governance:** The Polylaunch governance framework is a flexible system that allows the community to propose and vote on ecosystem initiatives such as new features, and key protocol parameters such as the fee structures discussed above. The community also has the power, if supported by an overwhelming majority, to refund any ongoing Polylaunch.

**Access:** Launchers are able to add a minimum requirement for $PL token balance for supporters to contribute to their sale. 

## 7 What about ...

**_Launcher’s could accumulate all of the venture bonds and initiate a refund vote_**

Each venture bond has its own market and order book programmed into it. Owners choose who exactly they want to sell to rather than going directly to the highest bidder. Additionally, if the venture bond didn’t exist, launchers would just have to buy 51% of the fungible tokens, so the venture bonds act as an additional layer of defense.

**_Supporters will enact refund votes even when launchers aren’t malicious if the token price is losing value compared to other crypto assets_**

In order to lower the chances of this happening, contributions are done using stablecoins. Were this not the case, if the sale was done with the native asset of the blockchain the launch is based on as is typical (e.g. ETH on Ethereum), if the Ether price skyrockets people may want to claw their ETH back. Using stable coins means the value contributed remains constant. 

**_Launchers may spend funds on lambos instead of actual work_** 

The first step to preventing this is not increasing the flow rate by more than is reasonably required. In addition, the threat of refund allows contributors to demand greater transparency and accountability of the use of project funds. If the balance sheet is unclear or clearly being misused, propose a refund. Polylaunch enables transparent on-chain accountability; we expect investors will monitor project progress and communicate off-chain if they feel milestones are not being reached and project investment should be reverted.

**_A 51% attack may maliciously enact a refund_**

In the unlikely event of a 51% attack to steal project funds, the launch team can start another Polylaunch and their supporters can contribute to the new launch. The attacker would still be limited to withdrawing only at the current flow rate as they would not be able to propose a flow rate increase without having access to the launch team’s private keys.

**_Supporters may keep starting refund votes and voting on them to increase their stream rates_**

The contributor flow rate will only increase at most once per month, regardless of how many times an address has voted in that period.

**_Launchers may amass 51% of the voting power and prevent refund votes from passing while increasing the tap and withdrawing funds_**

The community of $PL holders can propose and vote to refund any ongoing launch specifically for cases such as this, if a large enough majority is in favour of it.

## Future

In the immediate future, we plan to add support for whitelisting which will enable third-party KYC, and support more types of sales such as dutch auctions and bonding curve offerings. Moreover, the composable nature of much of the system as it is today allows for any number of interactions with the DeFi ecosystem. Venture bond backed loans, trading of venture bonds and additional venture NFT products such as options are all possible to build on top of the protocol.

### 8.1 Venture Options

While venture bonds are the initial venture NFT supported by the protocol, it isn’t the only type that will be supported. Venture option sales are a different type of Polylaunch where instead of receiving a stream of the underlying tokens over time, supporters purchase a Venture Option from a launcher, giving them the option, but not the obligation, to purchase tokens at a pre-agreed price directly from launchers. This launch method manages risk for both parties in unique ways: for the launchers, they have a guaranteed runway without risk of funds being revoked, due to the initial sale of the options. They can also receive additional funding from supporters exercising the options. For supporters, while they no longer have the right to a refund, they secure the option to purchase tokens at a potentially cut-rate price in future.

### 8.2 Philanthropy and Public Goods Funding

It’s important to note that Polylaunch is a protocol for decentralised fundraising - it is not limited to token sales. Funding for public goods and philanthropy can also benefit from the Polylaunch mechanism, where the supporters gain nothing in return except certainty that project funds will be released on a known schedule, accountability from the cause that they’re funding and their collectible NFT. 


