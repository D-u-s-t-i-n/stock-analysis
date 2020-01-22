# Challenge

The challenge asks for optimization for speed and potentially handling increased number of tickers. One obvious area of improvement is reducing the need to loop through the whole data set 12 (number of tickers) times. Four arrays were declared and an integer constant to "softcode" the 12 ticker count to allow for easier expandability and reduced repetitive code changes. When a new ticker gets added, the constant value can be changed otherwise the number 12 would have to be changed (at least 5 times) throughout the subroutine. I used a timer to time the time it took to process the 12 tickers using the original given template - it took around 0.5 seconds.

Since we are given that the ticker data is grouped alphabetically, I eliminate the outer loop and simply go through the inner data row loop (j) once while moving the tickerIndex into the loop. Since the data output row count (rows 4 to 15) and number of ticker elements (indices 0 to 11) are identical, I could have had the formatting loop and the array output assignment loop share the same for loop. But because the rubric mentioned a criteria of declaring four arrays before four loops. So I just kept the two formatting and array assignment loops separate. The processing time took around 0.12 seconds, almost 4x more efficient.


# Misc

The assignment does not state whether the arrays should be of type single or double. If single (float) arrays are used, then the volume values are different than that of the original module template (where no type was explicitly declared). It looks like arrays that are not declared (with Dim) are defaulted to double.