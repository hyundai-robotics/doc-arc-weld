# 4.1 Arc Welder communication settings


Follow the steps below to connect the PC and controller using an Ethernet cable:

1. Run the **Sycon** program on the PC.
2. Add the cifx card, then right-click its icon and select **configuration**.
3. Configure each items as follows:
  **Driver**: Set to nexX Driver
  **Bus Parameters**: Set Baud rate to 250kBits/s
  **Device Assignment**: Select the added cifx card and click OK.
4. Right-click the cifx icon and select **download**.
4. Right-click the cifx icon and select **network scan**.


![](../../_assets/4_1_1.png)<br>
*Figure 4.1.1. Sycon Communication Status*  

After completing the below steps, the sycon screen will appear as shown above. (when connected to Hyundai PNS Welder)

6. Right-click the welder icon and select **disconnect**, then go to **configuration > General > UCM** tab and set UCMM to Group3.
7. Right-click the welder icon and select **upload**, then right-click the cifx icon and select **download**.

On the Robot TP, navigate to `[F2: System] - 2: Control parameter - 2: Input/Output signal setting - 6: fb block allocation` and assign the blocks to be used.
Once this is completed, the data transmitted from the welder to the controller will be displayed in bold within the assigned blocks.
(Verify this in `[pane layout] - select - public input - assigned fb block`)


{% hint style="info" %}
  For more information, please refer to [${cont_model} - Industrial Communication](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/en/README?cont_model=${cont_model})  
{% endhint %}
