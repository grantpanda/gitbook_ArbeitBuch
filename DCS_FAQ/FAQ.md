Story 1:
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


Story 2:
	29 Cars in 2 order, finished gated out in AMS. And now found gated out from the wrong warehouse.

	    | VIN               | SO#            | LOT#         			 |
        | ----------------- | -------------- | ------------------------- |
		|LSJW74090LZ037592	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74090LZ040427	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74090LZ040492	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74091LZ040534	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74091LZ040842	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74092LZ036850	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74092LZ040428	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74092LZ040574	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74093LZ040390	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74093LZ040535	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74095LZ039600	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74095LZ040391	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74095LZ040536	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74095LZ040553	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74096LZ039380	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74096LZ040576	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74096LZ040822	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74097LZ039601	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74097LZ040554	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74098LZ040398	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74099LZ039597	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74099LZ040409	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74099LZ040488	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW7409XLZ038930	|4BNMG120735	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74094LZ030595	|4BNMG120801	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74094LZ039569	|4BNMG120801	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74094LZ041855	|4BNMG120801	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74096LZ030520	|4BNMG120801	 |CITYOFSTPETERSBURG 20200910|
		|LSJW74096LZ037838	|4BNMG120801	 |CITYOFSTPETERSBURG 20200910|

Summary:
	Generally has 3 process. Cancel Process, Transfer Process, Sales Process.

Operation Steps:
	1. Cancel Gate Out (This case done by IT team)
	2. Remove the cars from LOT. (Remember save the lot file)
	3. Cancel these 29 cars in DN list.
	4. Cancel these 29 cars in to-DN list.
	5. Create a new Transfer Order. (In this case , suppose it be TO# ABSMU120A03)
	6. Bind these 29 cars with TO# ABSMU120A03 in to-DN list.
	7. Create Delivery Notes for these 29 cars in DN list.
	8. Put them in transfer lot.(Caution: This is not the final lot for sales, it's lot for transfer process)
	9. Gate out 29 cars from AMS.
	10. Gate in 29 cars from ZEE.
	11. Bind these 29 cars with SO# 4BNMG120735 or SO# 4BNMG120801 according to the original record.
	12. Create Delivery Notes for 29 cars in to-DN list.(Manually create DN may be better)
	13. Put them in transfer lot.(Here use the lot file in step 2.)
	14. Gate out 29 cars from ZEE.
