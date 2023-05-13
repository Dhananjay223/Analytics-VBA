# Main Sub

This sub is the main entry point for the program. It first disables screen updating, events, and the status bar. This is done to improve the performance of the program by preventing Excel from updating the screen, processing events, and displaying the status bar while the program is running.

Once the screen updating, events, and status bar have been disabled, the sub enters a loop that iterates over all the cells in the active worksheet. For each cell, the sub calls the `linkGen`, `WebScraping`, `puller`, and `clearsheet` subs. These subs are responsible for generating a link to the Wikipedia page for the company name in the active cell, scraping the Wikipedia page for the company name, extracting the company headquarters address from the Wikipedia page, and clearing all the `QueryTable` objects and cells from Sheet1.

Finally, the sub enables screen updating, events, and the status bar. This is done to restore the normal behavior of Excel.

## linkGen Sub

This sub generates a link to the Wikipedia page for the company name in the active cell. It does this by concatenating the string "https://en.wikipedia.org/wiki/" with the value of the cell. The link is then copied to the clipboard and pasted into the cell.

For example, if the value of the active cell is "Acme Corporation", the sub will generate the link https://en.wikipedia.org/wiki/Acme_Corporation.

## WebScraping Sub

This sub uses the `QueryTable` object to scrape the Wikipedia page for the company name in the active cell. The sub first creates a new `QueryTable` object and sets its `URL` property to the link generated by the `linkGen` sub. The sub then sets the `WebSelectionType` property to `xlEntirePage` and the `WebTables` property to `1`. Finally, the sub refreshes the `QueryTable` object.

The `QueryTable` object is a powerful tool that can be used to extract data from web pages. In this case, the sub is using the `QueryTable` object to extract the company headquarters address from the Wikipedia page for the company name in the active cell.

## puller Sub

This sub extracts the company headquarters address from the Wikipedia page for the company name in the active cell. The sub first selects the cell containing the company name. It then iterates over the cells below the company name until it finds a cell that contains the text "Headquarters". The sub then copies the address from the cell above the "Headquarters" cell to the clipboard. Finally, it selects the cell on Sheet2 where the address should be pasted.

## clearsheet Sub

This sub clears all the `QueryTable` objects from Sheet1 and clears all the cells in Sheet1.

This is useful if you want to start fresh with the program.

*Variables*

* `url` - The link to the Wikipedia page for the company name in the active cell.
* `table` - A `QueryTable` object that is used to scrape the Wikipedia page.
* `address` - The company headquarters address.
* `i` - A loop counter.

*Loops*

* The `While` loop in the `Main` sub iterates over all the cells in the active worksheet.
* The `For` loop in the `puller` sub iterates over the cells below the company name until it finds a cell that contains the text "Headquarters".
