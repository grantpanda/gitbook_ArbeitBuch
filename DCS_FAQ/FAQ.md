Story:
	6 car now in Norway Sales Order in AMS, but need to gate out from ZEE.
        | VIN               | VC             | SO#         |
        | ----------------- | -------------- | ----------- |
        | LSJW7409XLZ037762	| MZKCSD29FCCWSB | 4BNMG120603 |
        | LSJW74090LZ039519	| MZKCSD29FCCPBC | 4BNMG120735 |
        | LSJW74092LZ039070	| MZKCSD29FCCRSJ | 4BNMG120735 |
        | LSJW74096LZ040416	| MZKCSD29FCCPBC | 4BNMG120735 |
        | LSJW74097LZ040537	| MZKCSD29FCCPBC | 4BNMG120735 |
        | LSJW74095LZ041718 | MZKCSD29FCCPBC | 4BNMG120801 |

Operation Steps:
	1. Pick out these cars ,got the VIN List of them.
	2. Create a Transfer order with QTY according to these 6 cars material code.(It's necessary to create transfer order first)
		|VC             | QTY |
        | ------------- | --- | 
        |MZKCSD29FCCWSB	| 1   |  
		|MZKCSD29FCCPBC	| 4   |
		|MZKCSD29FCCRSJ	| 1   |  
	3. Cancel these 6 cars in DN list.
	4. Cancel these 6 cars in to-DN list.
	5. Cancel all cars allocated by system under the transfer order in to-DN list.
	6. Bind 6 cars with the transfer order in to-DN list.
	7. Manually create DN, Create Transfer Lot, Gate out from AMS.
	8. Gate In 6 cars in ZEE.
	9. Bind 6 cars just to their own original SO# in to-DN list.
	10. Manually create DN, Create Sales Lot, Gate out from ZEE.
