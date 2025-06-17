# Governance

The IDRISS governance framework constitutes the primary decision-making system for both treasury management and technical upgrades. The DAO adopts a lightweight, secure, and efficient optimistic voting framework. Consequently, a formal proposal is assumed to have passed a vote unless it is explicitly vetoed by the community of IDRISS tokenholders.

#### Optimistic voting framework

1. **Proposal creation:** any community member, whether or not an IDRISS tokenholder, may put forward a proposal idea on [Discord](https://discord.com/invite/RJhJKamjw5).
2. **DAO council review:** currently comprised of 19 DAO Initial Members, who have been the signatories of the IDRISS token initiation transaction, the DAO council is responsible for championing a proposal idea to take shape as a formal proposal and progress to the voting stage. A simple majority of Initial Members is required for a proposal to progress.
3. **Voting:** the following parameters apply to all votes:

* Voting platform: [Snapshot](https://snapshot.box/#/s:idrissxyz.eth)
* Voting Power (VP) proxy and supply:
  * 1 IDRISS = 1 Voting Power
  * Voting supply is defined as all tokens actively held in user wallets, tokens added to the initial Uniswap v3 liquidity pool (Base: `0x6F9d09253f99d2B6843b5ec62C23496c37327216`), and lastly tokens that are locked in IDRISS vault contract (Base: `0x085e2dc1b05dcdbe011b5ad377c9f2fcd69b7057`), or to be locked in the IDRISS vault as per the retroactive distribution schedule on July 6, 2025.
* Veto quorum requirement:
  * IDFPs: 2/5 of the votable supply
  * IDIPs: 2/3 of the votable supply
* Votable supply is defined as `circulating supply` + `IDRISS tokens that are distributed into the IDRISS vault contract as per the retroactive distribution schedule` - `IDRISS DAO held liquidity position`.
* Vote options:
  * Abstain (VP not counted towards quorum)
  * Veto (VP counts towards quorum)

4. **Execution:** DAO Managing Members are responsible for including proposals on Snapshot for voting, as well as enacting the results onchain (via means of a 3/5 multisig wallet) and offchain.

<figure><img src="../.gitbook/assets/IDRISS governance flow.png" alt=""><figcaption></figcaption></figure>

#### Proposal frameworks

<details>

<summary>IDRISS Improvement Proposal (IDIP)</summary>

In order to become an IDIP, a proposal must contain the following sections and/or information:

* **Metadata (included separately):**
  * IDIP number
  * IDIP title
  * Date created
  * IDIP type (see IDIP categorization)
* **Abstract:** Serves as a short introduction to the proposal and should contain the summary of the motivation and specification sections.
* **Motivation:** Should describe the "why" of proposed changes.
* **Specification:** The most critical part of the proposal, this section should clearly and holistically lay out the proposed changes.
* **Backwards compatibility:** Where applicable, this section should describe whether or not, and to what degree, do the proposed technical changes retain backwards compatibility with existing systems.
* **Security considerations:** Where applicable, this section should inform of (and address) any and all security-related assumptions and perceived risks. In addition, it's recommended for proposal authors to exhaustively document risks as they arise during community feedback stage.
* **Copyright waiver:** All IDIPs must waive all copyright and related rights under the CC0 1.0 Universal license. An example of a copyright waiver to be included in a proposal:

> Copyright and related rights waived via the CCO 1.0 Universal license.\
> this.

#### IDIP categorization <a href="#idip-categorization" id="idip-categorization"></a>

IDIPs can be submitted in the following categories:

* **Metagovernance:** The governance framework may be changed via IDIPs in this category. Example decisions: amending the DAO's constitution or bylaws, changing voting rights, establishing or dissolving governance committees, altering quorum requirements, and adjusting proposal processes.
* **Contracts:** The IDRISS protocols require a set of contracts which may need to be upgraded both for security and protocol evolution purposes, e.g., IDRISS vault parameters.
* **Token:** The IDRISS token is an immutable ERC-20 token. However, some decisions may need to be made by the community in the future, e.g., contract migration, minting or burning tokens, altering tokenomics, and modifying token vesting schedules.

</details>

<details>

<summary>IDRISS Funding Proposal (IDFP)</summary>

In order to become an IDFP, a proposal must contain the following sections and/or information:

* **Metadata (included separately):**
  * IDFP number
  * IDFP title
  * Date created
* **Abstract:** Serves as a short introduction to the proposal and should contain the summary of the motivation and specification sections.
* **Motivation:** Should describe the "why" of proposed funding.
* **Specification:** The most critical part of the proposal, this section should clearly and holistically lay out the proposed funding. It's recommended to include the following:
  * funding amount
  * in-depth description of the proposed grant/expenditure
  * proposed impact reporting throughout the duration of funding, and post-funding, e.g., community calls, onchain and offchain data-driven reporting, etc.
* **Copyright waiver:** All IDIPs must waive all copyright and related rights under the CC0 1.0 Universal license. An example of a copyright waiver to be included in a proposal:

> Copyright and related rights waived via the CCO 1.0 Universal license.\
> this.

</details>

