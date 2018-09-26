## Update Validator's Metadata DApp

1. In MetaMask connect to the RPC endpoint of the required network:
   * Mainnet `Core`: https://core.poa.network
   * Testnet `Sokol`: https://sokol.poa.network

2. Select your **Voting Key** in MetaMask.

    **NOTE**: you must have a small amount of POA on your Voting Key to submit a transaction. During the initial ceremony, you must have received 0.1 POA on your Initial Key and can transfer it to Voting Key.

3. Open URL https://validators.poa.network - you should see a full list of validators who already joined the network.

4. Goto `SET METADATA` page.

5. Fill all the required fields with your contact details and license info.

    ![SetMetadataTab](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/validators_set_metadata.png)

    **NOTE**: title and footer of this page may be stylized differently, depending on the network you're connected to

6. Double-check the data you've provided.

7. Double-check in MetaMask that you've selected your Voting Key and you're on the required network.

8. Press `SET METADATA` button at the bottom of the page.

9. Confirm transaction in MetaMask.

10. Wait until the transaction is mined.

11. Open `PENDING CHANGES` tab and verify your data in the list.

12. Ask fellow validators to confirm and finalize your request. The metadata-change request needs at least 2 confirmations by different validators and then can be finalized by any validator including yourself. Finalizing a request commits changes to the network.

    ![PendingChangesTab](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/validators_pending_changes.png)
