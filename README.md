# Challenge

The challenge asks for optimization for speed and potentially handling increased number of tickers. One obvious area of improvement is reducing the need to loop through the whole data set 12 (number of tickers) times. Four arrays were declared and an integer constant to "softcode" the 12 ticker count to allow for easier expandability and reduced repetitive code changes. When a new ticker gets added, the constant value can be changed otherwise the number 12 would have to be changed (at least 5 times) throughout the subroutine. I used a timer to time the time it took to process the 12 tickers using the original given template - it took around 0.5 seconds.

Since we are given that the ticker data is grouped alphabetically, I initially wanted to eliminate the outer loop and simply go through the data row loop (j) once while modifying and adding more conditional if statements to ensure the ticker index is correctly tracked. But because the rubric mentioned a criteria of declaring four arrays before four  loops. So I used an alternative method of keeping the nested loop and instead added an Exit For and a starting variable replacing the initial j=2 to ensure the data is looped once. The processing time took around 0.28 seconds.

Another loop (seemingly unnecessary but improved speed for some reason) was added, which moves the data output out of the original nested loop. This extra loop should not increase processing time, but serves more for readability (ie: a stand-alone loop dedicated for output array assignment and display). This fifth loop resulted in the new modified AllStockAnalysis subroutine to take < 0.2 seconds to process. I will consult office hours to determine better understanding of this 0.8 second delta.

# Misc

The assignment does not state whether the arrays should be of type single or double. If single (float) arrays are used, then the volume values are different than that of the original module template (where no type was explicitly declared). It looks like arrays that are not declared (with Dim) are defaulted to double.