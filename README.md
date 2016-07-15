# GameOfLife
java project

@ TASK:

Game of life using double buffering
	- table of NxM, where 1 represents living cell, 0 dead
	- at each new generation, we apply the following rules:
		For a space that is 'populated':
			Each cell with one or no neighbors dies, as if by solitude.
			Each cell with four or more neighbors dies, as if by overpopulation.
			Each cell with two or three neighbors survives.
		For a space that is 'empty' or 'unpopulated'
			Each cell with three neighbors becomes populated.
	
	- initial random distribution, P(living cell) = 0.5f
	- P threads want to compute each frame in parlallel (you can consider that each thread computes 1 cell for simplity, but with 2 points penalty).

	Hints:
		Watch for race conditions on tables ! (borders !)
		Use a barrier to not allow a thread do work for a new cycle until all threads finished previous cycl
		Double buffering means you can have 2 tables: one frame you write on table A and read from B then at the end of the frame you switch tables.
