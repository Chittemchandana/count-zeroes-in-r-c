# count-zeroes-in r-c
# Python program to count number 
# of 0s in the given row-wise
# and column-wise sorted 
# binary matrix.

# Function to count number 
# of 0s in the given
# row-wise and column-wise
# sorted binary matrix.
def countZeroes(mat):
	
	# start from bottom-left
	# corner of the matrix
	N = 5;
	row = N - 1;
	col = 0;

	# stores number of 
	# zeroes in the matrix
	count = 0;

	while (col < N):
		
		# move up until
		# you find a 0
		while (mat[row][col]):
			
			# if zero is not found 
			# in current column, we 
			# are done
			if (row < 0):
				return count;
			row = row - 1;

		# add 0s present in
		# current column to result
		count = count + (row + 1);

		# move right to
		# next column
		col = col + 1;

	return count;
	
# Driver Code
mat = [[0, 0, 0, 0, 1],
	[0, 0, 0, 1, 1],
	[0, 1, 1, 1, 1],
	[1, 1, 1, 1, 1],
	[1, 1, 1, 1, 1]];

print( countZeroes(mat));
